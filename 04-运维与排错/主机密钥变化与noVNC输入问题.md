# 主机密钥变化与 noVNC 输入问题

## 本次现象

SSH 连接 tyccc 时出现主机公钥与旧记录不一致。CloudCone 页面同时显示 re-booting，但远程屏幕可以登录，系统运行时间为 41 天。不能只凭控制台标签推断系统刚重启，也不能凭密钥变化直接判定攻击。

## 怎么处理

从 CloudCone 进入 tyccc 的管理页，再点 Terminal，登录远程屏幕。用 [[SSH与主机指纹]] 中的命令取得服务器本地指纹，与网络连接取得的新指纹比较。

本次电脑工具输入 noVNC 时会漏掉下划线。路径变成 `sshhostrsakey.pub` 后，命令报“没有那个文件”。看到这类错误先检查实际输入文字，不要立刻重装 SSH。

普通键盘输入正确路径即可。为了完成自动操作，本次使用了这两条等效命令：

```bash
find /etc/ssh -regex /etc/ssh/ssh.host.rsa.key.pub -fprint /tmp/tutorial-keypath
xargs -a /tmp/tutorial-keypath ssh-keygen -lf
```

第一条只把匹配的公钥文件路径写入临时文件，第二条把路径交给 `ssh-keygen`。正则中的点号匹配单个字符，所以不需要工具输入下划线。它没有读取或公开私钥。

## 结果与边界

两处 RSA SHA256 指纹一致，确认了此次连接取得的密钥就是可信控制台中该机器使用的密钥。项目使用单独的 known_hosts 固定此公钥，没有覆盖用户原来的全局记录。

这一步验证的是服务器身份，不是证明其系统中所有软件绝对安全。下一步仍需要检查现有服务和文件，再决定安装方式。

来源：[OpenSSH ssh-keygen](https://man.openbsd.org/ssh-keygen)、[GNU findutils 手册](https://www.gnu.org/software/findutils/manual/html_mono/find.html)。
