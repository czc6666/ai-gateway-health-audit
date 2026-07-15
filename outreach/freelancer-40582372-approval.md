# Freelancer 单客户投标审批包：NEVIE-GLOBAL

## 唯一采购现场

- 项目：AI Platform Recovery, Completion & SEO Optimisation
- URL：https://www.freelancer.com/projects/wordpress/platform-recovery-completion-seo
- Project ID：40582372
- 实时状态：Open，约 12 小时前发布，6 天后截止
- 预算：$70–170 USD，paid on delivery
- 当前竞争：44 bids，平均约 $155.32
- 买家明确要求：Phase 1 是 paid discovery/recovery/stabilization；必须有 inspection、recovery、critical corrections、documentation 和 measurable improvements，不能只交报告。

## 适配裁决

**B｜砍成 $170、7 天的 Phase 1 rescue milestone，不硬卖原来的纯网关审计。**

这是当前找到的最强真实付费现场，但与 `$100 / 48h / audit-only` Offer 不完全匹配。项目明确写了“NOT an audit-only project”。因此报价必须诚实改成：

- $170 固定价；
- 7 天；
- 先做公开可验证的前台/SEO/checkout 故障；
- 获得访问后再做只读架构/集成盘点；
- 只承诺修复双方书面确认的 1–2 个 P0/P1 缺陷，不承诺 7 天内完成全平台；
- 后续完整项目另报，不以低价诱导加价。

若拿下并交付，净额可能受 Freelancer 平台费影响；但平台正式下单/里程碑即构成真实 E5。

## 已完成的公开网站实测

### 三个具体问题

1. **Founder Card 的公开结账路径实际失败。**
   - 页面展示价格 `1€`，点击 `Acquérir` 后没有跳转到 Stripe。
   - 浏览器控制台出现：`Connection attempt failed: SyntaxError: Failed to execute 'json' on 'Response': Unexpected end of JSON input`。
   - 前端代码实际向 webhook 发送 `amount: 198`，与页面 `1€` 不一致；代码中另一个映射值又是 `129`。这是价格/checkout 数据源漂移，属于商业 P0。

2. **Cookie policy 入口 404，cookie 实现与合规表述冲突。**
   - `https://nevie-global.com/politique-des-cookies` 实测 HTTP 404。
   - 首页源码主动隐藏多个 cookie banner 类，同时自定义 banner 文案只提供“Accepter”，没有可见拒绝/偏好入口。
   - 控制台还报告 Meta Pixel currency 参数格式无效。

3. **生产前端资产与信息架构存在可复现问题。**
   - 控制台提示 `cdn.tailwindcss.com should not be used in production`。
   - Google Fonts CSS 被错误当作 `@font-face src` 使用，浏览器反复报 `Failed to decode downloaded font` / `OTS parsing error`。
   - 首页单页同时承载 founder offer、珠宝预售、AI/机器人 R&D、投资者叙事和企业服务，首屏没有把唯一购买路径讲清；这会放大 checkout 失败造成的信任损失。

## 恢复建议

**Partial recovery / partial rebuild，不全量重做。**

保留 WordPress/Elementor 内容、已存在的产品素材和可复用页面；优先把交易链、环境/价格单一事实源、日志与回滚做稳，再拆分内容架构。完整源码、Railway/PostgreSQL、n8n、Stripe/OpenAI 的结论必须等客户提供授权访问后再下，不凭前台猜测。

## Phase 1 固定交付（$170 / 7 天）

1. 公开资产 + 客户授权资产的 verified inventory；
2. checkout / n8n / Stripe 数据流图与价格单一事实源核对；
3. 修复双方书面确认的 1–2 个 P0/P1（优先 checkout 失败与 cookie 404/合规入口）；
4. WordPress/React/Node/PostgreSQL/Railway/n8n/OpenAI/API 风险登记，材料不足项标明 unable to verify；
5. technical SEO / information architecture 的前 10 项优先清单；
6. 测试证据、Git commit、部署/回滚说明；
7. A 恢复 / B 局部重建 / C 全量重建建议与后续真实预算。

### 排除项

- 不在 $170 内重做完整平台、UI、全部 SEO 页面或所有工作流；
- 不承诺排名；
- 不把客户凭据放入个人仓库/个人云；
- 未经书面确认不改生产；
- NDA 和客户自有账户访问在中标后按平台流程处理。

## 拟投标

- 金额：$170 fixed
- 周期：7 days
- Milestone：100%（仅在书面确认 Phase 1 范围后开工）

## 待发英文 Proposal

```text
NEVIE-SITE-REVIEWED

I recommend partial recovery / partial rebuild, not a blind full rebuild. The public site already contains valuable WordPress/Elementor content and product assets, but the commercial path needs stabilization before more features or SEO pages are added.

Three specific visible, reproducible problems:

1. The public Founder Card checkout fails. The page displays 1€, but clicking “Acquérir” does not reach Stripe; the browser logs an empty-JSON failure from the n8n checkout webhook. The frontend also sends amount 198 while another in-page price map contains 129. This is a P0 price/checkout source-of-truth problem.
2. `/politique-des-cookies` returns 404. The homepage hides several consent-banner implementations and exposes only an Accept action in the custom banner, while Meta Pixel also logs an invalid currency parameter. Consent, tracking and legal links need one coherent implementation.
3. The production frontend loads `cdn.tailwindcss.com` and defines Google Fonts CSS URLs as font-file sources, causing repeated font decode/OTS errors. The homepage also mixes founder offers, jewelry, R&D, investor content and enterprise services without a single primary journey.

My first technical priorities:
- preserve and inventory client-owned assets;
- trace checkout → n8n → Stripe → PostgreSQL/Railway with a single price source;
- add structured request IDs, failure logging and rollback checks;
- fix 1–2 agreed P0/P1 defects, starting with checkout and the cookie-policy path;
- verify WordPress, React/Node, PostgreSQL/Railway, n8n, OpenAI/API integrations only after authorized access—anything not evidenced will be marked “unable to verify”.

First SEO / information-architecture priorities:
- separate Shop / Founder Offers / AI & Automation / Partnerships;
- repair legal/canonical/redirect paths and crawlable commercial journeys;
- validate sitemap, schema, metadata, internal links and analytics consent;
- create no city/service pages until each page has original evidence and a clear intent.

Phase 1 offer: $170 fixed, 7 days.
Included: verified inventory, architecture/checkout map, 1–2 agreed critical fixes, tests and commits in NEVIE-owned repositories, deployment/rollback notes, top-10 SEO/IA backlog, remaining-work estimate, and evidence-backed A/B/C recommendation.
Excluded: a complete platform rebuild, all workflows/pages, ranking guarantees, or production changes outside the written milestone.

I work independently, with AI-assisted analysis but human-verified evidence and no client credentials in personal systems. Relevant public evidence: https://github.com/czc6666/ai-gateway-health-audit

Proposed milestones:
1. Access/inventory + written acceptance criteria
2. Reproduce and map critical failures
3. Implement the agreed 1–2 fixes in client-owned staging/repositories
4. Test, document, demonstrate and recommend the next phase

Main risks: inconsistent price IDs/amounts, undocumented n8n/Stripe ownership, missing staging parity, and broad scope. I control these with a written Phase 1 boundary, backups, staging-first work and explicit rollback evidence.
```

## 风险与停止条件

- 这是 44 人竞争的真实平台项目，赢标概率不高。
- 用户当前没有已登录 Freelancer 账户；创建/登录实名平台、接受条款、投标和收款均需用户参与/授权。
- 本次只申请对 Project 40582372 投一条 $170 / 7 天 Proposal，不投其他项目。
- 未中标不追骚扰买家；中标后任何 NDA、凭据、生产访问另行最小审批。
