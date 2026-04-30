# AGENTS.md — Bin Ziyin (宾梓吟) 学术个人主页

> 本文件是给 AI coding agents（Claude Code / Codex / Cursor / Aider 等）的项目入口文档。任何工具接手前请先完整读完本文件。
> 主体中文，technical terms 与 proper nouns 保留英文。

---

## 1. 项目目标

为复旦大学 OM (Operations Management) 方向 PhD 候选人 **宾梓吟（Bin Ziyin / Ziyin Bin）** 搭建学术个人主页，目标是：

- **2026 年下半年** academic job market 期间正式启用
- 用途：会议、talk、interview 后让招聘委员、合作者通过搜索快速定位到本人
- 风格：简洁、专业、信息密度高（参考 fashengxu.com / qiaowenguo.com）
- 域名：`ziyinbin.com`（待购）
- 同步建立：Google Scholar / SSRN（已有）/ ORCID / ResearchGate（可选）档案
- LaTeX CV：在 `cv/` 子目录维护源码，编译产物自动发布到网站

---

## 2. 项目当前状态（State）

| 项 | 状态 |
|---|---|
| academicpages 模板已 clone | ✅ |
| 删除 demo 内容（5 假 paper / 4 假 talk / portfolio / blog / **_teaching demo / files demo PDFs / talkmap / unused _pages**） | ✅ 完整清理 |
| `git init` 完成 | ✅ （首次 commit 见 §11 任务清单） |
| `CNAME` 文件（含 `ziyinbin.com`） | ✅ |
| `.ruby-version` (3.3.4，对齐 GitHub Pages 生产环境) | ✅ |
| `cv/` 子目录（`cv.tex`, `awesome-cv.cls`, `Makefile`, `README.md`, `.gitignore`） | ✅ 已基于 CV PDF 预填；手机号已注释；多处 TBD |
| `_publications/2025-integrated-hedging.md` (WP1) | ✅ SSRN 链接 + 4 coauthors + abstract |
| `_publications/2025-photovoltaic.md` (WP2 framework) | ✅ 框架就绪，待补 coauthors + abstract |
| `_talks/*.md` (10 个文件) | ✅ 框架就绪，月份/城市需用户校准 |
| `_config.yml` 个性化 | ✅ author / url / social / publication_category 已填，github username 待 confirm |
| `_pages/about.md` 首页 | ✅ 含 placeholder bio（用户应替换为最终版） |
| `_data/navigation.yml` 简化 | ✅ Research / Talks / CV 三项 |
| `INFO_TO_PROVIDE.md` 问卷 | ✅ |
| `README.md` 项目说明 | ✅ |
| `.gitignore`：`简历/` PII 排除 + Baidu sync 元数据 | ✅ |
| 头像 `images/profile.png` | ❌ 待用户提供照片 |
| Paper 2 完整信息 (coauthors / abstract / SSRN) | ❌ 待用户提供 |
| 个人英文 bio 终稿 | ❌ 待用户替换 about.md 的 placeholder 段 |
| Conference 月份 + 主办城市 | ❌ 待用户校准 _talks/*.md |
| 域名购买 + DNS 配置 | ❌ 待用户操作 |
| GitHub repo 创建 + push | ❌ 待用户在 ziyinbin 账号下创建 `ziyinbin.github.io` |
| Google Scholar / ORCID / ResearchGate 注册 | ❌ 待用户操作 |

> 顶层 `简历/` 文件夹是用户提供的现有 CV（中英文 docx + pdf），AI agent 可以读取作为参考，但**不要修改或移动**这个文件夹。

---

## 3. Tech Stack

| 层 | 选择 | 链接 |
|---|---|---|
| Static Site Generator | **Jekyll** + **academicpages** template | https://github.com/academicpages/academicpages.github.io |
| Hosting | **GitHub Pages** (free, 自动 HTTPS via Let's Encrypt) | https://docs.github.com/en/pages |
| Domain Registrar | **Cloudflare Registrar**（推荐，~$10/yr at-cost）或 Porkbun | https://www.cloudflare.com/products/registrar/ |
| LaTeX CV Template | **awesome-cv**（XeLaTeX 编译） | https://github.com/posquit0/Awesome-CV |
| Local LaTeX | TeX Live 2026（已装） | — |
| Local Ruby/Jekyll | 系统 Ruby 2.6.10 太旧；建议 `brew install rbenv` 装 Ruby 3.2+ | — |

---

## 4. 用户身份信息（已从 CV 提取，待用户确认）

```yaml
chinese_name: 宾梓吟
english_name: Bin Ziyin           # 或 Ziyin Bin（given-first 国际惯例）
preferred_name_for_publications: TBD   # 学术发表用哪种顺序待确认
email: zybin23@m.fudan.edu.cn
phone: NOT_PUBLIC                 # 实际手机号在本地 CV 源文件外存储；不写入任何会推送到公开 repo 的文件
github: https://github.com/ZoeBin   # 用户考虑是否换 Gmail 账号重开

current_affiliation:
  institution: Fudan University
  school: School of Management (管理学院)
  program: PhD Candidate, Management Science (管理科学)
  start: 2021-09
  status: 硕博连读 (joint master-PhD program)
  expected_graduation: TBD

prior_education:
  - institution: Beijing Normal University
    school: School of Government
    program: BS, Management Science
    period: 2017-09 to 2021-06
  - international:
      institution: UC Berkeley
      type: Summer Program
      period: 2019-07 to 2019-08

advisor: TBD                        # CV 未注明，待用户提供

honors:
  - 复旦大学博士生学业奖学金一等
  - 复旦大学硕士优秀学业奖学金
  - 复旦大学"优秀学生"
  - 北京师范大学京师一等奖学金
  - 全国大学生数学竞赛三等奖
  - 北京高校数学建模校级联赛二等奖

skills:
  software: [Mathematica, Python, R, MATLAB]
  english: [CET-4 685, CET-6 583]
```

### Working Papers（来自 CV，需补充第二篇）

1. **Integrated Hedging Strategies for Exchange Rate and Commodity Price Risks**
   - Role: 第一作者 (first author)
   - Period: 2023.01–present
   - Status: working paper（用户称已上 SSRN，需补 SSRN URL）
   - Conferences (口头报告):
     - Supply Chain Finance & Risk Management Workshop, Olin Business School, Washington University in St. Louis
     - CSAMSE
     - POMS-HK
     - POMS-China
   - 待补字段：coauthors, abstract, SSRN link, latest revision date, target journal

2. **[第二篇 working paper - TBD]**
   - 用户在初次需求中提到"两篇工作论文"，但 2025-07 的 CV 仅显示一篇
   - 需要：title / coauthors / abstract / status / conferences

### 研究经历（科研项目）

- 国家自然科学基金重大项目《供应链韧性与安全基础理论》—— 科研助理 (RA), 2022.07-present
- 重大公共卫生事件冲击下 A 股市场行业间风险的传播与演化（基于复杂网络视角）—— 项目核心成员, 2020.03-2020.05
- 基于 SRISK 方法的我国金融风险计量与防范——结合银行间网络分析 —— 国创项目负责人, 2019.05-2020.05
- 基于动态模型的政府大数据交易定价机制研究 —— 校创项目负责人, 2018.05-2019.05

### 实习经历

- Nielsen, Data Analyst Intern, 2020.12-2021.02
- 中信建投期货 Trading Department Intern, 2019.08-2019.09

---

## 5. 信息缺口（What we still need from the user）

| 类别 | 待补信息 |
|---|---|
| **个人** | 头像照片（≥ 400x400 正方形）、英文 bio (100-200 词)、是否公开手机号、办公地址 |
| **导师** | Advisor 全名 + 主页链接（可多个） |
| **第二篇 working paper** | title / coauthors / status / abstract / conferences |
| **第一篇 working paper 补充** | SSRN URL / coauthors / abstract / target journal |
| **JMP** | Job Market Paper 是哪一篇（如已定） |
| **Research Interests** | 3-5 个英文关键词 |
| **Teaching** | 是否有 TA / Instructor 经历（CV 未列） |
| **Service** | 是否有 ad-hoc reviewer 经历 |
| **账号** | Google Scholar URL（如已有）、ORCID iD（如已有）、ResearchGate URL（如已有）、最终 GitHub username |
| **域名** | 确认 `ziyinbin.com` 拼写无误，是否已购买 |

---

## 6. 目录结构

```
Personal Website/                      # repo root（最终推送到 GitHub）
├── AGENTS.md                          # ← 本文件（AI tool 入口）
├── README.md                          # 给人类读者的项目说明（待重写）
├── _config.yml                        # ← 核心配置：姓名/邮箱/社交/导航
├── _config_docker.yml
├── Gemfile                            # Ruby 依赖（jekyll + plugins）
├── CNAME                              # 待创建：内容是 "ziyinbin.com"
│
├── _data/
│   ├── navigation.yml                 # 顶部导航条
│   ├── ui-text.yml
│   └── authors.yml
│
├── _pages/                            # 各主页面 markdown
│   ├── about.md                       # 首页（headshot + overview）
│   ├── publications.md                # Research 列表入口
│   ├── talks.md                       # 参会经历列表入口
│   ├── cv.md                          # 在线 CV（链接 PDF）
│   ├── teaching.md
│   └── ... (404, archive, search)
│
├── _publications/                     # 每篇 paper 一个 .md
│   ├── 2024-hedging-strategies.md     # WP1
│   └── 20XX-second-paper.md           # WP2 待填
│
├── _talks/                            # 每次 talk 一个 .md
│   └── YYYY-MM-conference-name.md
│
├── _teaching/
├── _portfolio/                        # 默认有，academicpages 给 ML 人用，OM 可删
├── _posts/                            # blog 文章（OM 一般不用，可删）
├── _layouts/                          # HTML layouts，一般不改
├── _includes/                         # partial templates
├── _sass/                             # 样式
│
├── files/
│   ├── cv.pdf                         # ← LaTeX 编译产物自动复制到此
│   └── papers/                        # 论文 PDF（如果上传 self-hosted）
│
├── images/
│   ├── profile.png                    # 头像（待用户提供）
│   └── favicon.ico
│
├── cv/                                # ← 待创建：LaTeX awesome-cv 子目录
│   ├── cv.tex
│   ├── awesome-cv.cls
│   ├── fonts/
│   ├── sections/
│   ├── Makefile                       # `make` → 编译 + 复制到 ../files/cv.pdf
│   └── README.md
│
├── markdown_generator/                # academicpages 自带：BibTeX → markdown 工具
├── scripts/
├── assets/
└── 简历/                              # ⚠️ 用户原始 CV 文件，勿动
    ├── 【中文简历】宾梓吟_v2507.docx
    ├── 【英文简历】Bin Ziyin_v2411.docx
    └── 简历_宾梓吟.pdf
```

---

## 7. 开发工作流

### 7.1 本地预览（Local Preview）

```bash
cd "/Users/bzy/Documents/baidu_snyc/Personal Website"
bundle install                         # 第一次需要装依赖（~3 分钟）
bundle exec jekyll serve --livereload  # 启动 dev server
# 浏览器打开 http://localhost:4000
```

> ⚠️ macOS 系统 Ruby 是 2.6.10，过旧。**建议先**：
> ```bash
> brew install rbenv ruby-build
> rbenv install 3.2.0
> rbenv local 3.2.0    # 在项目目录设置
> gem install bundler
> ```

### 7.2 编辑内容

- **改首页**：编辑 `_pages/about.md`（YAML front matter + Markdown body）
- **加论文**：在 `_publications/` 新建 `.md`，front matter 必须含：
  ```yaml
  ---
  title: "Paper Title"
  collection: publications
  permalink: /publication/2024-paper-slug
  date: 2024-MM-DD
  venue: "Working Paper / Journal of XXX"
  paperurl: "https://ssrn.com/..."
  citation: "Bin Z. (2024). Title. Working Paper."
  ---
  Abstract goes here.
  ```
- **加 talk**：在 `_talks/` 新建 `.md`，类似结构

### 7.3 编译 LaTeX CV

```bash
cd cv
make            # 等价于 xelatex cv.tex && cp cv.pdf ../files/cv.pdf
make clean      # 清理 .aux/.log/.out 等中间文件
```

### 7.4 部署 (Deploy)

```bash
git add -A
git commit -m "your message"
git push origin main
# GitHub Pages 自动构建（~2 分钟），访问 https://ziyinbin.com
```

---

## 8. 关键文件清单（Critical Files）

实施时请优先关注这些文件：

| 文件 | 作用 | 优先级 |
|---|---|---|
| `_config.yml` | 站点全局配置（author / social / nav / SEO） | P0 |
| `_pages/about.md` | 首页内容（headshot + bio） | P0 |
| `_data/navigation.yml` | 顶部导航条目 | P0 |
| `_publications/*.md` | 每篇论文一个文件 | P0 |
| `_pages/cv.md` | 在线 CV 页（链接 PDF） | P1 |
| `_talks/*.md` | 参会经历 | P1 |
| `cv/cv.tex` | LaTeX CV 主文件 | P1 |
| `cv/Makefile` | CV 编译流程 | P1 |
| `CNAME` | 自定义域名（一行：`ziyinbin.com`） | P2（域名购入后） |
| `images/profile.png` | 头像 | P0（用户提供后） |

---

## 9. DNS / GitHub Pages 配置（域名买入后）

### Cloudflare DNS 记录

| Type | Name | Value | TTL |
|---|---|---|---|
| A | @ | 185.199.108.153 | Auto |
| A | @ | 185.199.109.153 | Auto |
| A | @ | 185.199.110.153 | Auto |
| A | @ | 185.199.111.153 | Auto |
| CNAME | www | `<github-username>.github.io` | Auto |

### GitHub Repo 设置

1. Repo Settings → **Pages** → Custom domain 填 `ziyinbin.com` → Save
2. 等 DNS check 通过（~10 分钟）
3. 勾选 **Enforce HTTPS**（自动 Let's Encrypt 证书）
4. 仓库根目录的 `CNAME` 文件应已存在，内容为 `ziyinbin.com`

---

## 10. 已知陷阱（Gotchas）

- 🚧 **Ruby 版本**：系统 Ruby 2.6.10 不能跑现代 Jekyll，必须升到 3.0+（rbenv）
- 🚧 **GitHub Pages 构建白名单**：只支持白名单 Jekyll plugins。academicpages 默认配置已合规，**不要随便加 plugin**
- 🚧 **Repo 命名**：用户站推荐命名为 `<username>.github.io`（user site），fallback URL 更干净
- 🚧 **DNS 传播**：24-48h，期间用 `https://<username>.github.io` 临时访问
- 🚧 **academicpages 默认含 ML 风格内容**（portfolio/blog/talkmap），OM 候选人可以删 `_portfolio/`、`_posts/`、`talkmap*` 简化
- 🚧 **目录名带空格** `Personal Website` —— Bash 命令记得 `cd "..."` 加引号
- 🚧 **简历/ 文件夹** —— 是用户的原始 CV 备份，**只读不动**
- 🚧 **国内访问**：GitHub Pages 在国内偶尔被墙；如果对国内访问有要求，可后续加 Vercel 镜像

---

## 11. 任务清单（Next Actionable Tasks）

按依赖排序，AI agent 可以从上往下执行：

1. ✅ Clone academicpages 模板，删除全部 demo 内容
2. ✅ 写 AGENTS.md / README.md / INFO_TO_PROVIDE.md
3. ✅ `git init`，首次 commit（fresh history）
4. ✅ `cv/` LaTeX 脚手架 (awesome-cv) + Makefile
5. ✅ `_config.yml` 个性化（author / url / publication_category）
6. ✅ `_pages/about.md` 写 placeholder bio
7. ✅ `_data/navigation.yml` 简化为 Research / Talks / CV
8. ✅ `_publications/*.md` × 2 (Hedging WP1 完整 + Photovoltaic WP2 框架)
9. ✅ `_talks/*.md` × 10 (按时间倒序，月份/城市待校准)
10. ✅ `.ruby-version` 3.3.4（对齐 GitHub Pages）
11. ✅ PII cleanup（手机号从 AGENTS.md / cv.tex / INFO_TO_PROVIDE.md 撤掉）
12. **[待用户输入]** 用户提供：头像 / 英文 bio 终稿 / Paper 2 abstract & coauthors / conference 月份校准
13. **[待用户操作]** 注册 GitHub username `ziyinbin`，创建 `ziyinbin.github.io` repo
14. **[待用户操作]** 购买域名 `ziyinbin.com`（推荐 Cloudflare Registrar）
15. **[待 AI]** 用户的 GitHub username 一旦确认 → 加 git remote → 推送
16. **[待 AI]** 本地 `bundle exec jekyll serve` 验证渲染（依赖用户 `rbenv install 3.3.4`）
17. **[待用户操作]** Cloudflare DNS 配置（5 条 record）
18. **[待用户操作]** GitHub Pages Settings 启用 custom domain + Enforce HTTPS
19. **[待用户操作]** 注册 Google Scholar / ORCID（注册后填回 `_config.yml`）

---

## 12. 时间表（Timeline，参考 plan 文档）

| 阶段 | 内容 | 预计完成 |
|---|---|---|
| D0 | 用户提供基础信息 + 头像 | 5/1 |
| D1 | 域名购买 + repo 创建 + DNS 配置 | 5/2 |
| D2-D4 | v1 内容填充（about / publications / talks） | 5/3-5/5 |
| D5 | LaTeX CV 完整 | 5/6 |
| D6 | Google Scholar / ORCID 主页串联 | 5/7 |
| D7-D8 | SEO + 移动端 polish | 5/8-5/9 |
| **🚀 v1 上线** | `https://ziyinbin.com` 公开 | **~5/10** |
| Post-launch polish | bibtex 自动化 / 加 blog / 修文案 | 5/10-5/20 |
| Job market 启动前 | 更新 JMP / reference letters | 2026-08 |

---

## 13. 参考资源（References）

- academicpages 模板文档：https://academicpages.github.io/markdown/
- academicpages 源码：https://github.com/academicpages/academicpages.github.io
- awesome-cv：https://github.com/posquit0/Awesome-CV
- GitHub Pages 自定义域名：https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site
- Jekyll 官方文档：https://jekyllrb.com/docs/
- 完整规划文件：`/Users/bzy/.claude/plans/job-market-om-phd-glowing-hartmanis.md`
- 参考站点：
  - https://www.fashengxu.com/research （Wix，付费）
  - https://www.qiaowenguo.com/home （Google Sites）
  - https://sites.google.com/a/junli/ （Google Sites，最简）

---

## 14. 给 AI Agent 的协作约定

- **写代码前**：先 `Read` 本文件 + `Read` 当前 `_config.yml`
- **改 `_config.yml`**：保留 academicpages 默认结构，只替换 author / url / social 等字段
- **加 paper / talk**：直接在对应 `_*` 目录新建 `.md`，不要改 `_layouts/`
- **遇到 LaTeX 问题**：xelatex 编译失败时，检查中文字体（macOS 用 PingFang SC），必要时 fallback 到 pdflatex + 英文 only
- **不要**：擅自删除 `简历/` 文件夹；擅自改 `_layouts/` 或 `_sass/`（除非用户明示要求换风格）；提交带有 `<your-name>` 之类占位符的代码到 git
- **每次完成一个 milestone**：更新本文件 §2 状态表
