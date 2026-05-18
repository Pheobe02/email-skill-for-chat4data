---
name: customer-email
description: >
  Use this skill whenever the user needs to draft a customer support email for Chat4Data.
  Triggers include: user complaints about data extraction failures, speed issues, agent not
  understanding instructions, feature requests, subscription/payment problems, or any
  customer feedback requiring a response. Also trigger when the user says "help me reply to
  this customer", "draft an email", "write a support reply", or pastes a customer message.
  Always apply this skill before writing any customer-facing email for Chat4Data support.
---

# Chat4Data Customer Email Skill

## About Chat4Data
Chat4Data is an AI-powered Chrome extension that lets users extract structured data from
websites by describing their needs in natural language — no coding required. It supports
academic research, business data collection, and workflow automation.

---

## Latest Product Update (2026-04-21)

When drafting extraction-related replies, you can reference the **v3.0.0** capability upgrade
released on **2026-04-21** when relevant.

### v3.0.0 Core Improvements

1. **Cross-region extraction**: extract fields from multiple page areas in one task
2. **Dynamic interaction execution**: supports click/filter/input/pagination with model-driven exploration
3. **Human-in-the-loop**: users can adjust requirements in natural language during execution; agent pauses for login/captcha/manual steps and then resumes
4. **XPath backup + semantic validation**: model-generated XPath with algorithm fallback, plus semantic checks and auto-repair for higher stability

### When to mention v3.0.0 in customer emails

- Customer reports extraction failure on complex pages (especially login-required, multi-region, or interaction-heavy pages)
- Customer says fields are missing (for example title/price/review not fully extracted)
- Customer asks whether this scenario is already improved in the latest version

Suggested handling:
- Ask or confirm they are on **v3.0.0**
- Recommend upgrading first, then retry
- If still failing, ask for target URL and a short masked recording for follow-up

---

## Core Principles

1. **Always thank first** — acknowledge the user's effort in reaching out or providing feedback
2. **Empathize before explaining** — recognize the inconvenience before diving into technical details
3. **Be warm, not stiff** — conversational and human, not corporate
4. **Be specific, not vague** — explain the actual root cause found, not generic apologies
5. **Always close with a next step** — either ask for more info, or tell the user what happens next
6. **Language follows the customer** — output Chinese draft first, then translate to the customer's language
7. **Follow explicit user scope first** — if the user asks only for subject / only one language / only polishing, do exactly that

---

## Knowledge Base — How to Use

Before drafting any reply, **always look up the relevant reference file** for similar past cases.
This ensures the reply inherits real, battle-tested phrasing rather than generic templates.

### Lookup Logic

| Issue Type | Reference File |
|---|---|
| 采集失败 / Can't extract data | `references/cases-extraction-failed.md` |
| 提速 / Speed up extraction | `references/cases-speed.md` |
| Agent 不理解指令 / Agent misunderstands intent | `references/cases-agent-intent.md` |
| 功能超出范围 / Out of scope | `references/cases-out-of-scope.md` |
| 支付 / 订阅问题 / Payment issues | `references/cases-payment.md` |
| 功能路线图 / Feature roadmap | `references/cases-roadmap.md` |
| GDPR / 账号删除请求 / Account deletion | `references/cases-account-deletion.md` |

### How to Apply Past Cases

1. Read the matching reference file
2. Find the case most similar to the current customer's situation
3. Use that case's phrasing and structure as the starting point
4. Adapt to the specific details of the current customer — never copy verbatim
5. If no similar case exists, fall back to the templates in this file and **add the new case to the reference file afterward**

### Case Logging Rule (硬性新增)

- 默认流程：先输出邮件草稿给用户确认，**确认后**再写入对应 `references/cases-*.md` 文件。
- 若用户未确认、或明确要求“暂不落库”，禁止提前写入案例库。
- 每次客户确认通过后，都必须把该案例沉淀到对应 `references/cases-*.md` 文件（无论是否已有相似案例）。
- 新增案例至少包含：客户问题摘要、排查结论、回复语言、发送的回复、效果/下一步。
- 若同一问题有语言规范纠偏（如“客户为西语却误回英文”），必须在新增案例中明确记录，防止复发。
- 若本轮用户只要求“主题”或“润色”，也要记录为轻量案例（标注“输出范围受限”）。

---

## 读取客户来信截图的规则

当用户上传内部 Group 邮件截图时，**只读取以下 2 个字段**，其余一律忽略：

| 读取 ✅ | 忽略 ❌ |
|---|---|
| Email（客户邮箱） | First Name / Last Name / Company / Job Title |
| Message（客户留言） | Create Time / Account credits / Token usage / From IP / Language / 其他所有字段 |

> 客户姓名从 Email 前缀推断；客户语言以截图中 Message 内容为准。
> 若输出范围包含邮件正文或完整草稿，回复内容最前面必须先单独输出客户邮箱，格式：`客户邮箱：xxx@xxx.com`。

---

## Workflow Before Writing

### 第一步：判断用户是否已提供排查结论

**情况 A — 用户已明确告知结论**（例如："帮我回复这个用户，他需要的功能暂不支持，会在 Q2 支持"）
→ 直接进入起草邮件，无需询问。

**情况 B — 用户只转发了客户来信，未说明结论**（涉及采集失败、功能异常、Agent 行为等需排查的问题）
→ **强制暂停，先向用户询问排查结果**，收到回复后再起草邮件。

询问模板：
> 「我已读取客户来信。在起草回复之前，请告知您排查后的结论：
> - 问题原因是什么？
> - 是否有后续处理计划或解决方案？
> 收到后我会将结论优化语言并融入邮件回复中。」

### 第二步：确认基础信息

- 客户姓名（从 Email 前缀推断）
- 客户来信语言（从 Message 内容判断）
- 核心问题类型
- 客户当前插件版本（若为采集异常，优先确认是否已升级到 v3.0.0）
- 目标网址（若涉及采集问题且未提供，提醒用户索取）
- 用户当前要产出的范围（完整邮件 / 仅主题 / 仅改写 / 仅英文或仅中文）
- 若为账号删除/GDPR：是否已完成删除、是否需身份确认、承诺处理时效（例如确认后 24h）

> **铁律：涉及采集问题，未获得排查结论前，不输出正式邮件。**

### 第三步：确认输出格式（新增）

默认输出：
- 必须先给邮件主题（Subject）
- 再给邮件正文（中文 + 客户语言）
- 双语输出时，必须给出两套可直接发送内容：
  - `Subject（中文）+ 中文正文`
  - `Subject（客户语言）+ 客户语言正文`

若用户明确指定范围，按用户要求覆盖默认输出：
- 只要主题：仅输出主题候选，不附正文
- 只要某一种语言：只输出该语言
- 只要润色：保持原结构，仅做措辞优化
- 只要简短回复：输出精简版本，不自动扩写

硬性要求：
- 若已读取到客户邮箱，且输出范围包含正文/完整草稿，必须将 `客户邮箱：xxx@xxx.com` 放在最前面（先于 Subject）。
- 只要输出的是“邮件正文”，就必须包含 `Subject`
- 禁止输出“无主题”的完整邮件
- 用户要求“双语”时，禁止只给一套 Subject

### 第四步：确认后再落库（新增）

- 先提交邮件草稿（按用户要求的语言与范围）供用户确认。
- 仅在用户明确确认后，才可将该案例写入对应 `references/cases-*.md`。
- 若用户提出修改意见，先迭代文案，待最终确认后再落库。

### 快捷模式（新增）

触发条件：
- 用户仅提供一句或一小段排查结论，并明确让你“回复客户/起草邮件”
- 结论已包含可执行信息（原因 + 当前状态/后续动作至少其一）

默认行为（无需追问）：
- 直接输出可发送成品：`Subject + 中文正文 + 客户语言正文`
- 若客户语言未知，默认输出中文 + 英文
- 若客户语言已明确（例如西语），第二语言必须使用该语言，禁止回退为英文

例外：
- 用户明确说“只要主题 / 只要单语 / 只要润色”，按用户要求覆盖快捷模式

---

## Email Structure

```
Subject: [Clear and specific subject]

Hi there,


[Line 1: Thank you + acknowledge]

[Line 2–N: Address the issue with specific findings]

[Line N+1: Next step — what you'll do, or what you need from them]

[Optional closing warmth]

--
Best Regards,
[Agent Name]
Chat4Data team
```

---

## Subject Rules (新增)

1. Subject 要直接对应问题与站点/功能，例如：
   - `跟进您的反馈：docs.google.com 页面采集问题说明`
   - `Update on Your Extraction Issue on docs.google.com Pages`
2. 不要使用过于空泛的主题（如“Re: issue”）。
3. 若用户给了主题方向（如“跟进你的反馈”），在其基础上补全关键信息（问题类型 + 目标站点）。
4. 若用户明确“只要主题”，提供 1-3 个可直接发送的选项。

---

## Common Scenarios & Templates

### 1. Can't Extract Data (Root Cause Found)

Use when: investigation reveals a specific reason (feature boundary, special page structure,
multi-step interaction required, anti-scraping, login wall, etc.)

**中文草稿：**
```
Hi there,


感谢您使用 Chat4Data 并联系我们！

我们已对您遇到的问题进行了排查。[具体说明排查到的原因，例如：该页面的数据加载方式较为特殊，
需要模拟多步骤页面交互才能触达目标字段，而这一能力目前尚在开发中。]

[如有后续计划]：这项功能我们正在积极推进，预计 [时间] 上线。上线后我们会第一时间通知您。

如果您有其他采集需求，欢迎随时告知目标网址和需要采集的字段，我们可以提前为您验证。

期待您的回复！
```

**Common root cause phrases:**
- Feature boundary: "该功能目前尚不在 Chat4Data 的支持范围内"
- Special page structure: "该网页采用了特殊的渲染结构，暂时无法被正常采集"
- Multi-step interaction needed: "您描述的场景需要多步骤自动化网页探索能力，该能力正在开发中"
- Anti-scraping triggered: "为保证采集稳定性，我们在每个步骤间设置了合理的等待时间，以避免触发目标网站的反爬机制"

**If this matches v3.0.0 improvements:**
- Add an explicit retry step: "我们已在 2026-04-21 发布 v3.0.0，增强了页面探索与识别能力，请先升级后重试。"
- Keep next-step fallback: if still failing, request URL + masked recording

---

### 2. Can't Extract Data (Root Cause Unknown / Site Inaccessible)

Use when: the team cannot reproduce the issue, cannot access the site, or needs more info.

**中文草稿：**
```
Hi there,


感谢您的反馈，也对您遇到的问题感到抱歉！

我们尝试排查了您提到的情况，但目前暂时无法复现/无法访问该网站。为了更好地帮助您，
能否提供以下信息？

- 目标网址（如有登录限制，请告知）
- 问题发生时的截图或录屏（敏感信息可打码处理）

有了这些信息，我们可以更有针对性地为您排查。感谢您的配合！
```

Optional addition when likely related to old version:
- "也请先确认您已升级到 v3.0.0（2026-04-21 发布）后再试一次。"

---

### 3. Speed Up Extraction Request

Use when: user asks why extraction is slow or how to speed it up.

**Two sub-scenarios:**

**A. User needs list + detail page extraction simultaneously:**
> Recommend Pro plan — supports up to 3 browser tabs running simultaneously.

**B. User only needs list data:**
> Explain that a moderate wait time between steps is intentional to avoid triggering
> anti-scraping mechanisms, ensuring stable results.

Always ask for their specific scenario first if unclear.

---

### 4. Agent Doesn't Understand Natural Language Instructions

Use when: the AI agent misinterprets or fails to act on the user's instruction.

**中文草稿：**
```
Hi there,


感谢您的反馈，对于使用过程中遇到的困扰，我们深感抱歉！

能否告知您希望采集的网址，以及您在 Chat4Data 中输入的具体指令？这样我们可以
直接复现您的场景并排查问题所在。

期待您的回复！
```

---

### 5. Request Outside Chat4Data's Scope

Use when: user asks for a feature Chat4Data doesn't provide (e.g., translation,
Google Sheets sync, scheduling — unless roadmap update is available).

**中文草稿：**
```
Hi there,


感谢您使用 Chat4Data 并分享您的使用场景！

Chat4Data 是一款 AI 驱动的 Chrome 插件，专注于帮助用户通过自然语言描述，
从网页中提取结构化数据，无需任何编程基础。适用于学术研究、商业数据采集等场景。

您提到的 [具体需求] 目前不在我们的功能范围内，建议使用专门的工具来满足这一需求。

如果您有网页数据采集的需求，欢迎告知目标网址和需要采集的字段，我们很乐意为您提供帮助！
```

### 5.1 当前插件暂不支持的能力（统一口径，新增）

Use when: root cause is confirmed as current product limitation (e.g., canvas rendering pages,
unsupported interaction pattern, unsupported website architecture).

**中文草稿：**
```
Hi there,


感谢您的反馈，也抱歉给您带来不便！

我们已完成排查，您遇到的问题属于当前插件暂不支持的能力范围（[简要写明原因]）。

我们已经记录了您的需求，并会持续优化这类场景的兼容能力。

如果您有其他采集场景，也欢迎发给我们，我们可以先帮您做可采集性验证，并给您可执行建议。
```

**English draft:**
```
Hi there,


Thank you for your feedback, and sorry for the inconvenience.

After investigation, this issue falls into a capability that is not supported by our extension yet ([brief root cause]).

We have recorded your request and will keep improving compatibility for this type of scenario.

If you have other extraction scenarios, feel free to share them with us. We can help validate feasibility first and suggest a workable approach.
```

---

### 6. Feature on Roadmap

Use when: user requests a feature that is planned but not yet released.

**中文草稿：**
```
Hi there,


感谢您联系我们，也非常感谢您分享您的使用场景！

您提到的 [功能描述] 与我们的产品规划高度一致。我们目前计划在 [Q2/具体时间]
开发并发布这项功能。功能上线后，我们会第一时间通知您，让您成为最早体验的用户之一。

再次感谢您的反馈，这对我们的开发优先级判断非常有帮助！
```

---

### 7. Payment / Subscription Issue

Use when: user encounters checkout errors, declined payments, etc.

**中文草稿：**
```
Hi there,


感谢您联系我们，也感谢您的耐心！

我们已排查您的续费情况。[具体说明原因，例如：支付被拒是由于高风险支付环境，
交易被我们支付提供商的安全系统自动拦截。]

建议您尝试以下方式：
- 更换一张银行卡进行支付
- 使用常用设备或网络重新尝试
- 改用手机端而非桌面端完成支付

如果以上方式均无法解决，请告知我们，我们可以协助手动处理订阅。
```

### 8. v3.0.0 Upgrade Guidance (Extraction Quality / Login-Related Pages)

Use when: customer reports missing fields, unstable extraction, or login-related page extraction issues.

**中文草稿：**
```
Hi there,


感谢您的反馈，也抱歉给您带来不便！

我们已完成排查。针对这类页面场景，我们已于 2026 年 4 月 21 日发布 v3.0.0，重点增强了页面探索与识别能力（包括跨区域采集、动态交互执行、登录/验证码场景下的人机协作，以及 XPath 备份与语义校验机制）。

请先将插件升级到 v3.0.0 后再试一次。
如果升级后仍有问题，请回复目标网址和一段操作录屏（敏感信息可打码），我们会继续跟进处理。
```

**English draft:**
```
Hi there,


Thank you for your feedback, and sorry for the inconvenience.

We have investigated this case. For this type of page scenario, we released v3.0.0 on April 21, 2026, with stronger page exploration and recognition (including cross-region extraction, dynamic interaction execution, human-in-the-loop handling for login/captcha steps, and XPath fallback with semantic validation).

Please update the extension to v3.0.0 and try again.
If the issue persists after the update, please share the target URL and a short screen recording (you may mask sensitive information), and we will continue following up.
```

### 9. GDPR Account Deletion Request (Identity Verification First)

Use when: customer requests deletion under GDPR/Right to Erasure and internal conclusion is
"deletion not processed yet; identity confirmation required first; process within a defined SLA
after confirmation (e.g., 24 hours)".

**中文草稿（简洁版）：**
```
Hi there,


感谢您的来信。
为保障账户安全，请先回复确认您要删除的 Chat4Data 账户邮箱是 `[account_email]`。

收到确认后，我们会在 `[time_sla]` 内完成删除，并邮件通知您。

--
Best Regards,
[Agent Name]
Chat4Data team
```

**English draft (concise):**
```
Hi there,


Thank you for your message.
For account security, please reply to confirm that the Chat4Data account to be deleted is `[account_email]`.

Once we receive your confirmation, we will complete the deletion within `[time_sla]` and notify you by email.

--
Best Regards,
[Agent Name]
Chat4Data team
```

**Default placeholders:**
- `[account_email]`: same as sender email when customer explicitly states so
- `[time_sla]`: use exact commitment from internal conclusion (for example `24 hours`)

---

## Greeting Rule (新增)

1. 所有邮件正文称呼统一使用：`Hi there,`
2. 不再使用客户姓名称呼（如 `Hi [Name],` / `Hi [First Name],`）
3. 若用户明确指定其他称呼，再按用户要求覆盖

---

## Language Rules

1. By default, provide two drafts: Chinese + customer's language
2. Determine customer's language from the Message in the screenshot or the original message
3. Translate the full email into the customer's language
4. For Spanish: use formal register ("usted") unless customer used informal tone
5. For English: match customer's register (casual "Hi" → casual reply; formal → formal)
6. Never mix languages in a single email
7. If the user explicitly asks for one language only, follow the user's request
8. If customer's language is known and is not English, do not output English as the second draft
9. For bilingual output, both language versions must include their own Subject line

---

## Final Self-Check Before Sending (新增)

在输出前，逐项自检（必须全部满足）：

1. 是否包含 Subject（只要有正文就必须有）？
2. 若是双语，是否为“中文 + 客户语言”而非“中文 + 英文”？
3. 若客户语言已识别为西语，是否使用西语正式语气（usted）？
4. 双语版本是否都包含完整结构（Subject + 正文 + 签名）？
5. 是否包含清晰下一步（要客户提供的信息或我们后续动作）？
6. 若问题属于采集异常场景，是否已优先确认/建议升级到 v3.0.0（2026-04-21）？

---

## Tone Calibration by Severity

| Situation | Tone |
|---|---|
| General question | Warm, helpful, brief |
| Minor bug / inconvenience | Apologetic but confident |
| Repeated issue / long wait | Extra empathetic, proactive update |
| Feature not supported | Honest + redirect to what we can do |

---

## Signature Format

```
--
Best Regards,
[Agent First Name]
Chat4Data team
```

---

## Key Reminders

- **Never reply without the target URL** if the issue involves extraction — always ask first
- **Never promise features without confirmed roadmap dates**
- **Always validate** the user's URL before diagnosing
- **For unsupported capabilities, always include**: `we have recorded your request` + `invite user to share other scenarios for pre-validation`
- **Screenshots/video**: request these when remote investigation is blocked (login walls,
  geo-restrictions, sensitive data) — remind users sensitive info can be blurred/masked
- **When investigation conclusion is already provided by teammate/user, do not re-ask redundant questions**
