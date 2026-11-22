# 我的技术文档

欢迎访问我的个人文档网站。本网站使用 MkDocs 构建，通过 GitHub Actions 自动部署到 GitHub Pages。

- 作者：maplen1ght
- 实践主题：静态文档自动部署
- [关于本项目](about.md)
- [使用指南](guide.md)
- [API 参考](api.md)

## 这个站点是怎么来的

这个网站的全部内容都来自本仓库 `docs/` 目录里的 Markdown 文件。每当我修改这些文件并推送到 `main` 分支，
GitHub Actions 会自动做三件事：安装依赖、用 MkDocs 构建出静态网页、把构建结果发布到 GitHub Pages。
整个过程不需要我手动上传任何文件，也不需要在本地执行部署命令。

我之所以选择这套方案，是因为它把「写内容」和「发布网站」彻底分开了：
我只需要关心 Markdown 写得对不对，构建和部署交给流水线去做。
如果构建失败，Actions 日志会明确指出是哪一步出了问题，排查成本很低。

## 站点结构

| 页面 | 文件 | 内容 |
| --- | --- | --- |
| 首页 | `docs/index.md` | 站点简介与结构说明 |
| 关于 | `docs/about.md` | 项目目标与技术组成 |
| 使用指南 | `docs/guide.md` | 日常修改和发布流程 |
| API 参考 | `docs/api.md` | 接口文档的写法示例 |

## 一句话总结

Markdown 负责内容，MkDocs 负责把内容变成网页，GitHub Actions 负责自动构建，GitHub Pages 负责托管访问。

第二次推送。
