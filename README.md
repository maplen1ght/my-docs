# my-docs

我的个人技术文档网站，使用 MkDocs Material 编写，通过 GitHub Actions 自动构建并部署到 GitHub Pages。

## 网站地址

https://maplen1ght.github.io/my-docs/

## 项目简介

本仓库包含四个页面的静态文档站点：首页、关于、使用指南、API 参考。
文档源码位于 `docs/`，站点配置为 `mkdocs.yml`，自动部署流程定义在 `.github/workflows/deploy.yml`。
推送到 `main` 分支后，工作流会自动安装依赖、构建站点并发布到 GitHub Pages。

## 个人实验报告

[个人实验报告](report/README.md)

## 目录结构

```text
my-docs/
├── .github/workflows/deploy.yml   # 自动构建与部署工作流
├── docs/                          # 文档源码，四页 Markdown
├── report/                        # 个人实验报告与截图
├── mkdocs.yml                     # MkDocs 站点配置
├── requirements.txt               # Python 依赖
└── .gitignore
```

## 本地预览

```bash
python -m venv .venv
.\.venv\Scripts\Activate.ps1     # Windows PowerShell
python -m pip install -r requirements.txt
python -m mkdocs serve
```

浏览器打开 http://127.0.0.1:8000/ 即可预览。

严格构建检查：

```bash
python -m mkdocs build --strict
```
