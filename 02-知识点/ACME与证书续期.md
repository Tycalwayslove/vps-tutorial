# ACME 与证书续期

ACME 是自动申请和更新证书的协议，acme.sh 是实现它的一个工具，Let’s Encrypt 是签发证书的机构。它们分别相当于办证流程、代办程序和发证机构。

本次使用 HTTP-01 验证：申请程序临时在 TCP 80 端口回答验证请求，发证机构从外部访问它，确认我们能控制这个 IP。验证成功后才签发证书。

80 端口不是代理服务必须使用的端口，也不是浏览器管理面板的端口。证书续期时仍要能完成验证，所以不能永久把验证路径堵住。

续期不只是“下载一个新文件”。完整链条是：定时任务运行 → 到续期窗口时重新验证 → 更新证书 → 复制到业务使用的固定路径 → 重载使用证书的程序。

本次固定路径为 `/root/cert/tyccc-ip/fullchain.pem` 与 `/root/cert/tyccc-ip/privkey.pem`，部署命令配置了续期后重启 `x-ui`。短期证书不能依靠偶尔想起来才手工续期。

检查证书有效期：

```bash
openssl x509 -in /root/cert/tyccc-ip/fullchain.pem -noout -dates
```

本次申请成功和定时配置存在，可以当场验证；未来某一次自动续期是否成功，需要到时检查日志。两者不能混为一谈。

来源：[acme.sh 官方安装与部署说明](https://github.com/acmesh-official/acme.sh)、[Let’s Encrypt 验证方式](https://letsencrypt.org/docs/challenge-types/)。
