# Obsidian 与双向链接

Obsidian 将一组本地 Markdown 文件当作“仓库 / vault”打开。这个词与 Git 仓库用途不同：Obsidian 负责阅读、链接和编辑，Git 负责记录修改历史。本次两者恰好使用同一个 docx 文件夹。

Markdown 是带少量标记的纯文本。例如行首 `#` 是标题，`[标题](网址)` 是链接。文件名后缀是 `.md`；这里目录名叫 docx，但里面不是 Word 的 `.docx` 格式。

`[[SSH隧道]]` 表示跳到同名笔记。Obsidian 的反向链接能显示哪些文章引用了它，让学习可以从一个概念慢慢延伸。图片放在 Assets，正文使用相对路径引用；搬走整个仓库时图片也一起搬走。

打开方式：启动 Obsidian → 打开本地仓库 / Open folder as vault → 选择本教程的 docx 文件夹 → 打开 README 或 [[学习路线]]。不要选择它上面的私人工作区目录，那里有真实账号。

来源：[Obsidian 仓库说明](https://help.obsidian.md/vault)、[内部链接](https://help.obsidian.md/links)。
