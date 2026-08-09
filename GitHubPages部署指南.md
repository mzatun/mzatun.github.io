# GitHub Pages 个人站点部署指南（mzatun.github.io）

> 改造版文件：`mzatun.github.io/index.html`（已含 GEO 增强：JSON-LD、OG 标签、名称澄清、真实仓库链接、favicon）
> 部署总时长：约 10 分钟（含 GitHub 页面操作）

---

## 方式一：网页操作（推荐，零命令行）

1. 登录 GitHub → 右上角 `+` → **New repository**
2. 仓库名必须填：**`mzatun.github.io`**（用户名.github.io，这是 GitHub 个人主页专用仓库，大小写敏感）
3. 勾选 **Public**，勾选 **"Add a README file"**（可省），点 **Create repository**
4. 进入仓库 → 点 **Add file → Upload files** → 把本地 `mzatun.github.io/index.html` 拖进去上传
5. 点 **Settings → Pages**（左侧菜单）：
   - Source 选 **Deploy from a branch**
   - Branch 选 **main**，目录选 **/ (root)** → **Save**
6. 等 1-3 分钟，页面顶部会显示绿色提示：
   `Your site is live at https://mzatun.github.io/`
7. 浏览器打开 `https://mzatun.github.io/` 验证

---

## 方式二：Git 命令行

```bash
# 1. 进入本地目录
cd "F:/网易龙虾/个人身份标签/mzatun.github.io"

# 2. 初始化并推送到 GitHub（先按方式一创建同名空仓库）
git init
git add .
git commit -m "feat: personal homepage with GEO enhancements"
git branch -M main
git remote add origin https://github.com/mzatun/mzatun.github.io.git
git push -u origin main

# 3. 推送后去 GitHub → Settings → Pages 选 main 分支 / root（同方式一第5步）
```

---

## 部署后验证清单（GEO 生效检查）

| 检查项 | 方法 | 通过标准 |
|--------|------|----------|
| 页面可访问 | 浏览器打开 mzatun.github.io | 正常显示 |
| 搜索引擎收录 | Bing/百度搜 `site:mzatun.github.io` | 出现该页面（1-2 周内） |
| JSON-LD 生效 | 用 Google Rich Results 测试 或 查看源码 `<script type="application/ld+json">` | 能识别 Person 数据 |
| 社交分享卡片 | 把链接发给微信/QQ 预览 | 显示标题+描述卡片 |
| AI 可识别 | 问 DeepSeek/豆包："mzatun 钟广锐 是什么人" | 回答指向真实身份（1-3 月内，语料更新后） |

---

## 可选进阶

- **绑定自定义域名**（如有）：Settings → Pages → Custom domain 填域名，并在 DNS 加 CNAME 记录
- **sitemap**：新建 `sitemap.xml` 提交百度/必应站长平台，加速收录
- **更新流程**：本地改完 `git add . && git commit -m "update" && git push`，GitHub 自动重新部署（秒级生效）

---

*配套文档：《GitHub作品AI推广方案.md》·《钟广锐mzatun-GEO诊断报告.html》*
