# AI 搜索与 AEO（源自 Ahrefs 指南第 9、10 篇）

> 原文：https://ahrefs.com/zh/seo/what-ai-means-for-seo · https://ahrefs.com/zh/aeo/how-answer-engines-work

## AI 改变了什么

- **零点击上升**：AI Overviews / AI 模式直接给答案，点击减少（美国 20%+ 关键词出 AI Overviews；2024 年 60% 的 Google 搜索以零点击结束）。
- **答案入口多元化**：ChatGPT、Perplexity、Gemini、Copilot 都会成为流量入口。
- **内容创作门槛降低**：同质化内容泛滥，独特性（信息增益）更值钱。
- **SEO 没死反而更重要**：AI 搜索依赖传统搜索索引与排名；**73% 出现在 Google AI Overviews 的网站位列自然搜索前十**——先排上去，才容易被 AI 引用。

## 答案引擎的工作原理（决定"怎么被引用"）

1. **两套知识**：训练数据（模型固有知识）+ 实时检索（RAG/事实锚定）。
2. **查询扇出（query fan-out）**：一个用户问题被扩展成多个相关问题分别检索 → **能覆盖大量相关子问题的页面被引用概率更高**。
3. **检索→分块→合成**：页面被切成内容块参与召回 → **内容要模块化**：一个小节独立讲清一个子问题，不要把关键信息埋在长段落里。
4. **引用选择标准**：
   - **相关性**：内容与答案中具体论断的直接支持程度（被检索≠被引用）
   - **新鲜度**：及时更新的内容更被青睐
   - **多样性**：引擎倾向引用多个不同来源——挤进"被引用集合"的机会是分化的

## ChatGPT 选择引用源看什么

URL、标题、摘要（通常是 **meta description**）、排名位置、元数据（如发布日期）——除排名外全部是页面可控因素。**把 title/URL/meta description/发布日期写干净、写准确，就是 AEO 的基础工程。**

## 技术侧（AI 可抓取性）

- 多数 LLM 爬虫**不渲染 JavaScript** → 核心内容服务端渲染
- robots.txt / Cloudflare 不要拦截 AI 爬虫（GPTBot、OAI-SearchBot、ClaudeBot、PerplexityBot 等）
- 结构化数据（Schema）帮助 LLM 正确解析页面（Google 与 Microsoft 均已证实）
- AI 引用的幻觉 URL 打 404 时，301 到相关页面挽回流量
- 搜索与 AI 都偏好新鲜内容——旧内容定期更新

## 策略清单（建站/写内容时落实）

1. 传统 SEO 做到位（排名是被引用的最大预测因子）
2. title/URL/meta description/发布日期四件套干净准确
3. 内容模块化：每节独立回答一个子问题（配合 FAQPage Schema）
4. 覆盖 query fan-out：围绕目标词把相关问题和长尾变体都答到
5. 提供信息增益：原创数据、亲测、专家引述（AI 倾向引用有价值且多样的来源）
6. 陈述句写作、结论前置（对精选摘要和 AI Overview 同样有效）
7. 允许 AI 抓取；多语言站考虑各语言版本分别优化
8. 监测 AI 可见度：定期在 ChatGPT/Perplexity/AI Overview 搜核心词与品牌名；分析竞品被引用而你缺席的页面，针对性重建内容
9. LLMs.txt 不用做（无证据有效）

## 心态

SEO 的目标从"排名"扩展为"**在搜索结果、AI 摘要、AI 对话引用中被提及**"。页面基础因素没变——好的页面 SEO 同时服务于 Google 和 AI 助手。
