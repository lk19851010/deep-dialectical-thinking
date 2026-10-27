# Deep Dialectical Thinking · 深度思考辩证技能

给 AI 编程助手用的"思维纪律" Skill（兼容 Claude Code / ZCode 等 Agent Skills 格式）：
强制走完 **调查研究 → 主客观切割 → 矛盾推演 → 自我辩证 → 实践迭代** 五步闭环，
并用一张 **病根诊断表** 把思考失败逐一定位到五种哲学病根上。

> **English**: A "thinking discipline" skill for AI coding agents, in the Agent Skills (`SKILL.md`) format. It enforces a five-step dialectical loop — investigation → fact/opinion separation → contradiction analysis → self-debate → practice iteration — and ships a diagnostic table that maps every failure symptom back to one of five root causes: dogmatism, empiricism, subjective assertion, one-sidedness, and static/isolated thinking. Content is written in Chinese.

## 它解决什么问题

AI 输出最常见的失败不是"不会写"，而是**想错了还不知道自己想错了**。五种典型病根：

| 病根 | 典型表现 |
|---|---|
| **教条主义** | 没查实际，拿通用模板直接套——"理论上应该这样" |
| **经验主义** | 拿上一个项目的经验套新任务；把项目私有内容污染进通用工具 |
| **主观臆断** | 为圆漏洞编造"惯例""设定"，把判断伪装成事实 |
| **片面化** | 只找支持自己结论的证据，从不主动找反例 |
| **静止孤立** | 局部成立、全局即崩；不考虑条件变化与关联传导 |

关键在于：**这些病根互相关联**——一个病根常同时引发多种症状，一种症状背后常有多个病根。所以本技能不是一堆散装条文，而是一张关联网：

```
发现症状 ──按表定位──▶ 病根 ──跳转──▶ 自检问题 / 纠正纪律
   ▲                                          │
   └────────── 出错后归档回诊断表 ◀────────────┘
```

## 内容结构

整个技能就是一个 [SKILL.md](SKILL.md)，六个模块：

| 模块 | 作用 |
|---|---|
| 一、病根诊断表（枢纽） | 五种病根 × 它是什么 × 典型症状 × 自检问题 × 纠正纪律 |
| 二、五步闭环 | 治病根的固定工序，第四步"自我辩证"（主动站到对立面）是核心环节 |
| 三、配套纪律条款 | 调查先行（违反即全部输出作废）／纠错响应（先认根因再修）／资产分离（防项目经验污染通用工具） |
| 四、输出格式规范 | 强制完整呈现思考过程，末尾带**失败留痕区**：试过跑不通的方向、被否的想法，全部列出，不删不藏 |
| 五、禁止性红线 | 绝对化表述、纯理论空谈、跳过调查、判断冒充事实等一票否决 |
| 六、常见失败模式速查 | 症状 → 病根对照表，按表诊断 |

## 安装

**Claude Code**（用户级，其他层级同理）：

```bash
git clone https://github.com/lk19851010/deep-dialectical-thinking.git
mkdir -p ~/.claude/skills
cp -r deep-dialectical-thinking ~/.claude/skills/
```

**ZCode**（用户级或项目级）：

```bash
cp -r deep-dialectical-thinking ~/.zcode/skills/
# 或项目级：<项目根>/.zcode/skills/
```

也可以最简使用：只把 `SKILL.md` 的正文并进你自己的系统提示词 / AGENTS.md。

## 怎么用

在需要严肃思考的任务上触发：研究、写作、规划、决策、方案评审……各工具按自己的 skill 调用方式使用（例如 ZCode 里 `$deep-dialectical-thinking`，Claude Code 里让模型按 skill 名调用）。

触发后它会强制 AI：

1. **动笔前先调查**：涉及现实机制、行业实务、平台规范的内容，查证不到不落笔；
2. **事实与观点彻底剥离**：主观判断必须标注"判断/假设"，必须挂事实支撑点，无事实支撑的判断不成立；
3. **主动站到对立面**：构建完整的反方立论，禁止刻意弱化对手；
4. **结论带适用边界**：成立的前提、范围、失效场景一并给出，新事实出现即修正；
5. **失败留痕**：输出末尾列出所有试错方向与残留疑问，供使用者参详。

## 适用场景

- AI 长文写作 / 内容生成前的背景调查与设定自检（查证平台规则、历史事实）
- 技术方案与架构评审：强制反方论证，防一面倒
- 制作通用工具 / 模板：防止单一项目经验污染通用资产
- 任何"AI 一本正经胡说八道"高发的任务

## 方法论来源

以辩证唯物主义认识论（调查研究、矛盾分析、实践检验）为根本框架，结合 AI 工程实践中反复出现的真实失败模式归纳而成。病根诊断表的"症状 → 病根 → 自检 → 纪律"结构，让每一次纠错都沉淀为可复用的资产，而不是修完即忘。

## 许可

[MIT](LICENSE)
