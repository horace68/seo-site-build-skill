# 技术 SEO 规则（源自 Ahrefs 指南第 1、2、7 篇）

> 原文：https://ahrefs.com/zh/seo/how-do-search-engines-work · https://ahrefs.com/zh/seo/seo-basics · https://ahrefs.com/zh/seo/technical-seo

## 工作原理（一切技术 SEO 的底层逻辑）

搜索引擎四步：**抓取（发现 URL）→ 处理与渲染 → 索引（进入可响应查询的页面库）→ 排名**。页面没被抓取或没被索引，后面全免谈。内链是发现页面的主要途径；sitemap 加速发现；反向链接影响排名。

## 域名 / 托管 / 平台选型（建站决策时）

- **域名**：简短易记的商家名/品牌名，不刻意塞关键词，不带连字符；TLD 对 SEO 无影响，但首选 **.com**（辨识度与信任度）；避开 .info/.biz（垃圾联想）；只服务单一国家可用 ccTLD（.fr/.es/.de）。
- **托管三 S + 一新**：安全（SSL/TLS）、服务器位置（靠近目标用户，或用 CDN 解决）、支持（响应及时）、**搜索与 AI 可访问性**（可自定义 robots.txt 与 sitemap、不屏蔽 AI 爬虫）。
- **平台**：自托管 WordPress 可定制性最强（配 Yoast/Rank Math 插件）；托管平台（Wix/Shopify/Webflow/静态生成器）SEO 能力如今也够用，选熟悉的。
- 服务器必须允许 Googlebot、Bingbot、GPTBot 等 AI 爬虫访问。

## 抓取控制

- **robots.txt**：声明允许/禁止路径 + sitemap 地址。禁止搜索引擎/AI 抓取 = 放弃相应流量与被 AI 引用的机会。
- **LLMs.txt：不做**——Ahrefs 结论：无证据表明有效，不值得投入。
- **crawl-delay**：Google 不理会该指令；要调 Google 抓取频率去 GSC 设置。
- 会员/测试环境用登录、HTTP 认证或 IP 白名单——不要用 robots.txt 防泄露（被链接的禁抓页仍可能被索引）。
- 抓取预算：热门与常更新的页面抓得勤；网站过载爬虫会自动降速。

## 索引控制

- **Meta robots**：`<meta name="robots" content="noindex">` 放 `<head>`；确认重要页面没有误加。
- **规范化（canonicalization）**：同一页面多 URL 时，Google 综合参考：canonical 标签、内链指向、301 重定向、sitemap 收录——**四处信号要一致**，都指向规范 URL。用 GSC 网址检查工具验证 Google 选了哪个规范 URL。

## 速胜清单（影响最大，优先做）

1. **检查索引**：希望有排名的页面必须被索引（GSC 网址检查 / Site Audit 可索引性报告）。
2. **找回丢失的链接**：改版后的旧 URL 若有外链，逐条 **301** 到新位置——最快的"链接建设"。
3. **补内链**：给已排名但缺内链的页面加内链；找有排名关键词的提及处做上下文相关内链。
4. **加 Schema**：见 on-page.md。

## 面向 AI 搜索的技术要求

- **多数 LLM 不渲染 JavaScript**：核心内容与导航必须是服务端输出的 HTML，否则 AI 爬虫看不到。SPA 站点考虑 SSG/SSR/预渲染。
- **检查第三方拦截**：Cloudflare 等默认可拦截 AI 爬虫（含训练类），要 AI 可见度就关掉拦截。
- **幻觉 URL**：AI 有时会引用你域名下不存在的 URL，发现 AI 来源流量打到 404 时，301 到相关有效页面。
- **AI 内容检测**：AI 辅助创作没问题，但大量低质 AI 内容可能被视为垃圾信号；上线前人工核对。
- **AI 工具注入的代码**：AI 编程工具可能往页面塞隐藏的 AI 类名/指纹代码（曾有 Yoast 漏洞案例）——**发布前检查源码，清理意外注入**。

## 页面体验信号

- **Core Web Vitals**：LCP（加载）、CLS（稳定）、INP/FID（交互）；用 PageSpeed Insights 检测。
- **HTTPS**：全站加密。
- **移动端友好**：移动优先索引；GSC「移动设备易用性」报告查问题（文字过小、点击目标过近）。
- **插页广告**：遮内容的弹窗会拖累排名。

## 多语言 / 多地区

- **hreflang**：每个语言版本页声明全部变体，**必须互指 + 自指**，语言代码合法（如 `en`、`de`、`zh-CN`）。
- 结构上子目录（`domain.com/de/`）通常优于子域名；主域权威可继承。

## 常规维护

- 失效链接（内/外链）定期清；重定向链拍平（一跳到位）。
- GSC：提交 sitemap、看抓取统计、网址检查、移动可用性报告。
- 旧 URL 有外链时一律 301 挽回权重。

## 工具清单

Google Search Console（必装，免费）、Bing Webmaster Tools、PageSpeed Insights、Google 移动友好测试、富媒体搜索结果测试（验证 schema）、Chrome DevTools、Ahrefs 免费版/Site Audit（可索引性、内链机会、失效链接）。

## 优先级心法

技术 SEO 是**及格线**：可抓取、可索引、快速、移动可用，做到位即可；大多数网站把时间投在**内容和链接**上回报更高。影响力最大的技术项目通常都与索引或链接有关。
