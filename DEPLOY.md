# 部署指南 (DEPLOY.md)

> 一次性的上线 checklist。完成后这个文件可以删，或保留作为日后切换域名 / 换账号的参考。

## 流程总览

```
1. 创 GitHub repo (你做，30 秒)         ← 见 README
2. 加 git remote + push (AI 做)
3. Cloudflare DNS 配置 (你做，照下面表格粘贴)
4. GitHub Pages Settings 启用 custom domain (你做，3 步)
5. 等 DNS 传播 + HTTPS 自动签发 (10 分钟 - 24 小时)
6. https://ziyinbin.com 正式可访问
```

---

## 1️⃣ DNS 配置（Cloudflare 控制台）

进入：Cloudflare Dashboard → 选 `ziyinbin.com` → 左侧 `DNS` → `Records` → `Add record`

**逐条添加下列 5 条**（每加一条点 Save，再 Add record 加下一条）：

| Type | Name | IPv4 / Target | Proxy status | TTL |
|---|---|---|---|---|
| **A** | `@` | `185.199.108.153` | **DNS only**（灰色云） | Auto |
| **A** | `@` | `185.199.109.153` | **DNS only** | Auto |
| **A** | `@` | `185.199.110.153` | **DNS only** | Auto |
| **A** | `@` | `185.199.111.153` | **DNS only** | Auto |
| **CNAME** | `www` | `ziyinbin.github.io` | **DNS only** | Auto |

⚠️ **关键**：所有记录的 Proxy status 必须设为 **DNS only**（灰色云），**不能是 Proxied**（橙色云）。
原因：GitHub Pages 自带 Let's Encrypt 证书自动签发，Cloudflare 代理 + GitHub HTTPS 同时开会引起证书签发循环失败。

⚠️ **如果同名记录已存在**（比如 Cloudflare 默认给的占位 A 记录），先 Delete 旧的再 Add 新的。

### （可选）IPv6 记录

如果想支持 IPv6 用户：再加 4 条 AAAA 记录，IP 分别是：
```
2606:50c0:8000::153
2606:50c0:8001::153
2606:50c0:8002::153
2606:50c0:8003::153
```
Name 都填 `@`，Proxy 都 `DNS only`。

### 验证 DNS 生效

```bash
dig ziyinbin.com +short
# 应该返回 4 个 IP：185.199.108-111.153
```

---

## 2️⃣ GitHub Pages 启用 custom domain

进入：https://github.com/ziyinbin/ziyinbin.github.io/settings/pages

1. **Source**: 应该已经是 `Deploy from a branch` → Branch `main` → `/ (root)` → Save
2. **Custom domain**: 输入框填 `ziyinbin.com` → Save
3. GitHub 会自动 DNS check：
   - ✅ 通过：会显示 `DNS check successful`
   - ⏳ 还在传播：等几分钟刷新页面
4. DNS check 通过后，**勾选** `Enforce HTTPS` 复选框
   - 此时 GitHub 自动调用 Let's Encrypt 签发证书（10-30 分钟）
   - 签发完成后，访问 `http://ziyinbin.com` 自动跳转到 `https://`

### CNAME 文件

仓库根目录的 `CNAME` 文件已含 `ziyinbin.com` —— 当你在 Settings → Pages 输入 custom domain 时，GitHub 会读这个文件确认。**不要手动改**这个文件。

---

## 3️⃣ 验证全链路

```bash
# 检查 DNS
dig ziyinbin.com +short
dig www.ziyinbin.com +short

# 检查 HTTPS 证书
curl -I https://ziyinbin.com

# 应该返回 HTTP/2 200，且 cert issuer 是 Let's Encrypt
```

浏览器测试：
- https://ziyinbin.com ← 主页
- https://www.ziyinbin.com ← 应自动 301 重定向到 ziyinbin.com（GitHub Pages 默认行为）
- https://ziyinbin.com/publications/ ← Research 页
- https://ziyinbin.com/talks/ ← Talks 页
- https://ziyinbin.com/cv/ ← CV 页
- https://ziyinbin.com/files/cv.pdf ← CV PDF（编译后）

---

## 4️⃣ 故障排查

| 现象 | 原因 | 解决 |
|---|---|---|
| `https://ziyinbin.com` 浏览器报"无法访问"超过 1 小时 | DNS 未生效 | `dig ziyinbin.com +short` 看是否返回 GitHub IP；不是的话回 Cloudflare 检查记录 |
| 证书警告 (NET::ERR_CERT_COMMON_NAME_INVALID) | DNS 已通但 HTTPS 证书未签发 | 等 30 分钟，或在 Pages settings 重新 toggle "Enforce HTTPS" |
| 显示 "404 - There isn't a GitHub Pages site here" | repo 名字不是 `ziyinbin.github.io`，或 `main` 分支没 push | 检查 repo 名，检查 git push 成功 |
| Cloudflare 显示 "Domain registration unavailable" | 注册后头几小时 Cloudflare 内部还在 propagate | 等 1 小时再试 |
| 自定义域名输入框灰色 | repo 没启用 Pages | Settings → Pages → Source 选 main branch + root |

---

## 5️⃣ 完成后

1. 删除本文件（已经过期），或挪到 `_drafts/` 留作归档
2. 把 `https://ziyinbin.com` 填到：
   - SSRN author profile (见 INFO_TO_PROVIDE.md D-bis 段)
   - 邮箱 signature
   - Google Search Console 申请收录
   - 复旦学院学生页（拜托管理员加链接）
3. AI 完成 SEO 加速三件事（schema、multi-name meta、sitemap）
