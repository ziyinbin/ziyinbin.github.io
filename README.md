# Bin Ziyin (宾梓吟) — Academic Personal Website

[ziyinbin.com](https://ziyinbin.com)（域名上线后生效）的源码仓库。

基于 [academicpages](https://github.com/academicpages/academicpages.github.io) Jekyll 模板搭建，托管于 GitHub Pages。LaTeX CV 在 [`cv/`](cv/) 子目录维护。

---

## 文档导航

| 文件 | 用途 |
|---|---|
| **[AGENTS.md](AGENTS.md)** | AI 编程助手（Claude Code / Codex / Cursor）的入口文档，描述项目状态、tech stack、目录结构、协作约定 |
| **[INFO_TO_PROVIDE.md](INFO_TO_PROVIDE.md)** | 用户需补充的信息清单（个人信息 / 论文 / 学术经历 / 账号） |
| **[cv/README.md](cv/README.md)** | LaTeX CV 编译说明 |

---

## 快速开始

### 本地预览

```bash
# 1. 升级 Ruby（系统自带 2.6.10 太旧，Jekyll 需要 ≥3.0）
brew install rbenv ruby-build
rbenv install 3.3.4   # 与 GitHub Pages 当前生产环境一致 (Jekyll 3.10.0)
cd "/Users/bzy/Documents/baidu_snyc/Personal Website"
rbenv local 3.3.4   # 已写入 .ruby-version 文件

# 2. 装依赖
gem install bundler
bundle install

# 3. 启动本地 dev server
bundle exec jekyll serve --livereload
# 浏览器打开 http://localhost:4000
```

### 编译 LaTeX CV

```bash
cd cv
make            # 编译 + 复制 PDF 到 ../files/cv.pdf
make view       # 打开 PDF
make clean      # 清理中间文件
```

### 部署

```bash
git add -A
git commit -m "Update content"
git push origin main
# GitHub Pages 自动构建（~2 分钟），ziyinbin.com 自动更新
```

---

## 项目状态

详见 [AGENTS.md §2](AGENTS.md#2-项目当前状态state)。

简言之：
- ✅ academicpages 模板已就位
- ✅ LaTeX CV 脚手架已就位
- ✅ 一篇 working paper (Integrated Hedging) 已录入
- ⏳ 待用户提供：头像、英文 bio、第二篇 paper、导师信息、conference 年月、honors 年份
- ⏳ 待用户操作：购买域名 / 创建 GitHub repo / 配置 DNS / 注册 Google Scholar & ORCID

---

## 致谢与授权

- 网站文案与 CV 内容：© Bin Ziyin
- academicpages 模板：MIT License
- awesome-cv 模板：CC BY-SA 4.0
