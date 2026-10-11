# seo-site-build-skill

**建站 / 网页开发时的 AI 编程 SEO 指导 skill**——让 Claude Code、ZCode、Codex、Cursor 等 AI 编程助手在你建站、写页面、上线部署时，自动按专业 SEO 规则开发并自查，而不是等上线后再补救。

内容提炼自 [Ahrefs《SEO 完全指南》](https://ahrefs.com/zh/seo)（中文版 10 篇）+ [AEO 指南](https://ahrefs.com/zh/aeo/how-answer-engines-work)，覆盖：关键词先行、搜索意图 3C、站点结构与 URL 规范、每页 On-page 硬规则（TDK/H1/内链/图片/Schema）、技术上线 Checklist（可抓取/可索引/CWV/AI 爬虫）、AI 搜索（AEO/GEO）专项、常见翻车红线。

## 它解决什么问题

AI 写代码很快，但默认不懂 SEO 约束，常见翻车：核心内容只能 JS 渲染（LLM 爬虫拿空壳）、URL 塞日期、每页多个 H1、robots.txt 拦了 AI 爬虫、上线忘提交 sitemap、AI 工具注入的隐藏代码不清理……这个 skill 把这些变成**开发期的检查项**。

## 安装

skill 本体就是仓库根目录的 `SKILL.md` + `references/`，clone 到对应 agent 的 skills 目录即可。

**通用路径（推荐，多数新式 agent 都认）**：

```bash
git clone https://github.com/horace68/seo-site-build-skill.git ~/.agents/skills/seo-site-build
```

**Claude Code**：

```bash
git clone https://github.com/horace68/seo-site-build-skill.git ~/.claude/skills/seo-site-build      # 用户级（所有项目）
git clone https://github.com/horace68/seo-site-build-skill.git .claude/skills/seo-site-build       # 项目级（单个项目）
```

**ZCode**：

```bash
git clone https://github.com/horace68/seo-site-build-skill.git ~/.agents/skills/seo-site-build      # 或 ~/.zcode/skills/
```

**Codex CLI / 其他读 AGENTS.md 的 agent**：clone 到任意位置后，在项目的 `AGENTS.md` 加一行：

```markdown
建站或写网页前，先读 /path/to/seo-site-build-skill/SKILL.md 并按其规则开发。
```

**Cursor**：Cursor 无原生 skill 机制，把 SKILL.md 的内容放进 `.cursor/rules/seo.mdc`，或同样在 `AGENTS.md` 里引用。

更新：`git -C <clone目录> pull` 即可。

## 使用

装好后正常对话即可触发（描述写得比较主动，说"建站""落地页"等就会命中），也可以显式调用：

```
/seo-site-build 帮我用 Astro 建一个 word counter 工具站，下周上线
```

典型行为：

- 开工前先要**目标关键词**（没给就先引导做关键词调研 + 搜索意图 3C 分析）
- URL/站点结构按规范设计；每个页面按 On-page 规则表写（title ≤70 字符、单 H1、alt、JSON-LD Schema…）
- 交付前跑一遍**技术上线 Checklist**（robots.txt、sitemap、canonical、SSR、AI 爬虫、CWV…）
- 有你自己的选词标准（如 KDRoi 阈值）时，优先按你的标准执行

## 结构

```
├── SKILL.md                        # 主规则：开发流程排列的硬规则 + 上线 Checklist + 红线
└── references/                     # 按需加载的深度参考（附 Ahrefs 原文链接，可溯源）
    ├── on-page.md                  # TDK/标题/内链/图片/Schema 完整规则（原第 5 篇）
    ├── technical.md                # 抓取/索引/canonical/CWV/hreflang（原第 1、2、7 篇）
    ├── content-keywords.md         # 关键词指标/优先排序/内容方法论/外链（原第 3、4、6 篇）
    └── ai-search.md                # 答案引擎原理与 AEO 策略（原第 9、10 篇）
```

## 致谢与版权

规则提炼自 Ahrefs 的公开 SEO 指南（作者 Joshua Hardwick、Ryan Law、Tim Soulo、Patrick Stox 等），原文见 [ahrefs.com/zh/seo](https://ahrefs.com/zh/seo)，版权归原作者所有。本仓库是对方法论的摘编整理，仅供学习交流；商用请遵循 Ahrefs 原文的使用条款。

## License

[MIT](./LICENSE)
