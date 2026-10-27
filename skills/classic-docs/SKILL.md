---
name: classic-docs
description: Writing style for documentation and code comments in Chinese. Covers terms, sentences, headings, explanation, and what to leave out. Use when writing or revising docs, doc sections, or code comments.
disable-model-invocation: true
---

# Classic Docs

State the facts a reader needs in order to judge for themselves. This is the test for every rule below: a rule that demands a particular section does not belong here; a rule that helps the reader understand behavior and limits does.

## Scope

- Treat this skill as a rule for how to write, not whether to write. Do not create or edit documentation files unless the user asks for documentation work.
- Write comments that explain purpose, non-obvious constraints, or behavior that cannot be read off the local code. Do not narrate each line of implementation.
  - For a function named `parseConfig`, 「解析配置」 has no value; 「只读取启动时的配置，运行期间不重新加载」 does.

## Language and terms

- Write docs in Chinese.
- Use ordinary words; do not coin short forms.
- Use an English term when it is more precise than the Chinese one, for example "agent" instead of 「代理」.
- Give each concept exactly one name and reuse it: the full name at first mention, the same name throughout. Do not write 「输出端口」 in one sentence and 「口」 in the next. Define terms in the glossary table when the page has one.
- Do not invent terms, abbreviations, or metaphors. If a word appears neither in the code nor in everyday Chinese technical writing, describe the thing in plain words.

## Sentences

Write the way an experienced Chinese engineer explains the system to a colleague. Follow natural Chinese word order; do not carry English sentence structure over word by word.

- Write complete, unambiguous statements. In instructions, an omitted subject is fine when the actor is clear. Do not omit the action, object, or condition needed to understand the sentence.
  - 「把请求转发给下一个服务」, not 「往下推」.
  - 「用请求里的标识找到对应的资源」, not 「按标识找」.
- Use concrete verbs. The single-character abstract verbs 「对」「收」「开」「走」「打」 carry no meaning alone.
  - 「两个服务报告的地址不一致」, not 「地址对不上」.
  - 「创建一条连接」, not 「开条连接」.
  - 「直接调用这个函数」, not 「打这个函数」.
- Keep the connective that carries a condition or a consequence. Do not shorten a sentence by dropping it.
- Write prose. Do not replace a sentence with fragments or compressed labels: concision removes unnecessary information, not necessary words.
- Address the reader when giving an instruction, but do not frame system behavior as something the reader can do.
  - 「客户端在超时后取消请求」, not 「你可以在超时后取消请求」.
- Avoid translationese such as 「进行了一次……的处理」「被……所……」「对于……而言」「不是……而是」. Name the actor and the action.
- Do not insert an aside with a dash mid-sentence. Split it into two sentences.

## Headings

- Name a definite subject: a concept, an API, an operation, a behavior, or a relationship between them.
- Use the established name of the subject, and the same name in heading and body.
- Match the scope to the section: neither wider than what the section explains nor narrowed to a detail without a subject of its own. Name the subject directly instead of leaving the heading vague.
- Prefer the topic name to a question, an instruction, a conclusion, or a sentence that introduces the text below.
- Let the heading locate the topic and the first paragraph state the behavior. Do not compress the whole sentence into the heading.

## Explanation

Explain what the system does, when it does it, and why, only as far as the reader needs in order to make a correct choice.

- Start from the behavior or concept the reader needs to understand. Introduce background only when it helps explain that behavior.
- Make relationships explicit: what triggers an action, what it changes, what it returns, and under which conditions. Include only the relationships the passage needs.
- Explain concepts through observable behavior. When a claim is hard to understand without an example, use a small, realistic one and say what it shows.
- State defaults, limits, failure cases, and the distinctions that affect how the reader uses or changes the system.
- Scale detail to the subject. A code comment may need one sentence; an unfamiliar concept may need several paragraphs.
- Let the subject determine the structure. Do not require every page or section to follow the same outline.

## What to leave out

- Do not praise the design, claim that a choice is intentional, or tell the reader the material is easy.
- Do not write rhetorical or personified lines.
  - 「返回 `invalid_input`，这次请求不会开始」, not 「不会猜着往下跑」.
  - 「无法恢复的任务直接记为失败」, not 「老实失败，不会假装还在跑」.
  - 「无法转换成 JSON 的对象会报 `payload_invalid`」, not 「不会偷偷转成字符串」.
- Do not leave editing traces: no intermediate reasoning, no change history, no sentence restating what the code already says. After a refactor, "business logic lives in `ctx.runs`" is an editing trace.
- Do not open with filler or comment on the text itself. Begin with the subject when no introduction is needed.
- Do not split one sentence across several bullets or table rows. Each is one complete statement.
