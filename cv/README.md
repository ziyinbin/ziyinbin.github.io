# LaTeX CV — Bin Ziyin

基于 [Awesome-CV](https://github.com/posquit0/Awesome-CV) 模板的学术 CV 源码。

## 编译

```bash
make            # 编译并将 cv.pdf 复制到 ../files/cv.pdf（网站下载链接指向此处）
make view       # 编译后用 macOS 默认阅读器打开
make clean      # 清理 .aux/.log 等中间文件
```

## 字体依赖

awesome-cv 默认用 **Source Sans 3**（Google Fonts）和 **Font Awesome 6**：

- Font Awesome 6：TeX Live 2026 已自带，无需安装
- Source Sans 3：如果编译报字体缺失，从 [Google Fonts](https://fonts.google.com/specimen/Source+Sans+3) 下载放入系统字体（macOS Font Book 直接拖入）

如果不想装字体，可以编辑 `awesome-cv.cls` 把 `\setmainfont{Source Sans 3}` 改成 `\setmainfont{Helvetica}`（macOS 自带）。

## 文件说明

| 文件 | 作用 |
|---|---|
| `cv.tex` | 主源文件，包含所有 section |
| `awesome-cv.cls` | LaTeX class（不要改，除非想换字体/颜色） |
| `Makefile` | 编译脚本 |
| `fonts/` | 自定义字体（如需）|

## 维护流程

1. 改 `cv.tex` 中对应 section 的内容
2. 跑 `make`
3. `cd ..` 然后 `git add files/cv.pdf cv/cv.tex && git commit -m "Update CV"`
4. `git push` —— 网站上的 CV 下载链接自动更新到最新版

## 待补充字段（cv.tex 中带 `TBD` 或 `20XX` 的地方）

- 导师姓名
- 各 honors 的具体年份
- Research interests 的关键词
- 第二篇 working paper 的全部信息
- ORCID iD（如已注册）
