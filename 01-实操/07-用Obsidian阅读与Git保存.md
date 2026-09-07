# 07 · 用 Obsidian 阅读与 Git 保存

服务器已经工作，教程还需要成为可维护的知识库。先读 [[Obsidian与双向链接]]、[[Git与版本控制]]。

## 打开正确的文件夹

在 Obsidian 的仓库选择器中，选择“打开本地仓库 / Open folder as vault”，打开本项目的 **docx** 文件夹。不是上一级工作区，也不是 Assets。找到 README，再点击 [[学习路线]]。

不懂的词点进去，读完用 Obsidian 返回按钮回来。图像打不开时，检查是否只下载了 Markdown 却没下载 Assets；克隆整个仓库会一起拿到它们。

GitHub 网页不原生支持所有 Obsidian 双链，因此网页看见 `[[...]]` 不代表本地链接失效。README 同时提供普通 Markdown 的章节入口，方便在 GitHub 阅读。

## 本次仓库关系

```text
私人工作区/
├── account.md       真实账号，不进入仓库
├── .private/        原始截图、备份、连接信息，不进入仓库
└── docx/            Obsidian 根目录，也是独立 Git 仓库
    ├── .git/
    ├── README.md
    ├── 01-实操/
    ├── 02-知识点/
    └── Assets/      可公开的脱敏截图
```

本次远程地址：`git@github.com:Tycalwayslove/vps-tutorial.git`。这里开头的 git 是 GitHub SSH 连接用户，后面的 Tycalwayslove 是仓库所有者；不是 tyccc 服务器的 root 账号。

## 已有本地仓库如何保存修改

在**电脑终端**进入 docx 目录，按顺序执行：

```bash
git status --short
git diff
git add README.md 00-导航 01-实操 02-知识点 03-协议 04-运维与排错 05-探索记录 06-参考资料 Assets
git diff --cached --stat
git diff --cached
git commit -m "docs: update VPS tutorial"
git push origin main
```

`status` 看改了哪些文件；`diff` 看未暂存修改；`add` 选中要存档的内容；`--cached` 查看待提交内容；`commit` 本地存档；`push` 上传 GitHub。图片不能靠文字 diff 检查，要打开实际查看。

这份仓库已经初始化过，不要再运行 `git init` 创建套在里面的第二个仓库。首次在另一台电脑取得教材可运行：

```bash
git clone git@github.com:Tycalwayslove/vps-tutorial.git
```

如果只是阅读公开教材，没有配置 GitHub SSH 密钥，也可使用 GitHub 的 HTTPS 克隆地址或下载 ZIP。修改之前用 `git pull --ff-only` 获取更新，若有本地未保存修改或分叉则先理解提示，不用强推覆盖别人历史。

## 安全保存的完成标准

提交前确认：真实 IP、账号密码、UUID、私钥、订阅 ID、连接二维码不在公开材料中；原始日志和数据库没有被跟踪；截图使用不可逆的实色遮挡并导出成独立图片。检查忽略规则不是检查历史的替代品。

查看 `git log --oneline -5` 可以找到最近存档点。远程失败时本地 commit 仍在；不必为了重新推送再次提交相同内容。恢复文档可从旧提交中取出特定文件，避免不理解 `reset --hard` 就执行。

来源：[Pro Git](https://git-scm.com/book/zh/v2)、[Obsidian 帮助](https://help.obsidian.md/)、[Git push](https://git-scm.com/docs/git-push)。
