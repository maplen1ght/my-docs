# 使用指南

本文说明日常如何修改文档、在本地验证，以及把改动发布上线。

## 完整流程

1. 修改 `docs` 目录中的 Markdown 文件。
2. 在本地预览并检查页面及链接。
3. 提交修改并推送到 `main` 分支。
4. 在 Actions 页面查看构建与部署状态。
5. 打开网站检查内容是否更新。

## 常用命令

- `python -m mkdocs serve`：启动本地预览服务器，默认地址 `http://127.0.0.1:8000/`，修改文件后浏览器会自动刷新。
- `python -m mkdocs build --strict`：构建网站并严格检查警告，出现死链或配置问题会直接报错退出。

## 各步骤的注意点

| 步骤 | 容易出错的地方 | 应对方式 |
| --- | --- | --- |
| 修改文档 | 页面间链接写成本地绝对路径 | 用相对路径，如 `about.md` |
| 本地预览 | 忘记激活虚拟环境，`python` 指向了别的版本 | 先执行激活命令再运行 |
| 提交推送 | 误把 `site/` 或 `.venv/` 加进暂存区 | 提交前先 `git status` 和 `git diff --staged` |
| 查看状态 | 只看网站不看 Actions | Actions 里 `build` 和 `deploy` 都变绿才算成功 |

## 本地预览的完整命令

```bash
# 创建并激活虚拟环境（Windows PowerShell）
python -m venv .venv
.\.venv\Scripts\Activate.ps1

# 安装依赖
python -m pip install -r requirements.txt

# 构建检查
python -m mkdocs build --strict

# 启动预览
python -m mkdocs serve
```

预览结束后按 `Ctrl+C` 停止服务。

## 什么时候会自动部署

只有以下文件被推送到 `main` 时才会触发工作流：

- `docs/**`
- `mkdocs.yml`
- `requirements.txt`
- `.github/workflows/deploy.yml`

也就是说，只改 `README.md` 或 `report/` 里的报告，网站不会重新部署，这是设计如此。
如果确实需要重新发布而代码没变，可以到 Actions 页面手动运行一次 `workflow_dispatch`。

## 相关链接

- 返回[首页](index.md)
- 了解[项目目标](about.md)
- 查看[API 参考](api.md)
