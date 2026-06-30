# 马哲分析工具箱

`marxist-analysis` 是一个面向 Codex / AI Agent 的马克思主义分析方法 Skill 方案。

它不是“马克思主义资料库”，也不是“马克思、列宁、毛、邓圆桌会谈”。它的目标是把马克思主义传统中的核心方法转化为一个可调用、可执行、可检验的分析工具箱：先看现实条件，找主要矛盾，拆利益结构，再落到实践方案。

## 项目定位

本项目要解决的问题是：当用户拿一个现实问题来问 AI 时，AI 不应该只是背诵概念、堆原文、模拟人物口吻，而应该能够按马克思主义的方法完成一次分析。

核心工作流是：

```text
现实条件 -> 问题分类 -> 主题调度 -> 人物来源校准 -> 矛盾与利益分析 -> 实践检验方案
```

更具体地说：

1. 先问清楚问题发生在什么现实条件下。
2. 判断这个问题属于政治经济、阶级国家、组织建设、群众路线、改革发展、意识形态，还是实践策略问题。
3. 先调用主题模块，再调用人物模块。
4. 区分主要矛盾和次要矛盾，区分矛盾的主要方面和次要方面。
5. 拆出生产力、生产关系、利益结构、组织条件、阶段约束。
6. 给出可以被实践检验的小方案，而不是停在口号或解释。

## 为什么不是人物扮演

马克思、恩格斯、列宁、毛泽东、邓小平等人属于同一理论传统，但他们面对的历史任务不同。

如果把他们直接合并成一个“马克思主义人格”，会出现三个问题：

- 不同阶段的问题被抹平，历史张力消失。
- 不同人物的判断条件被混成一个泛泛的声音。
- 用户问现实问题时，Agent 容易变成轮流模仿人物，而不是给出可执行分析。

所以本项目采用三层结构：

```text
人物蒸馏：保留差异
主题重组：形成工具
总控调度：按问题调用
```

也就是说，人物模块不是用来扮演的，而是用来提供来源、方法和历史张力的。

## 设计原则

### 1. 统一的是问题意识，不是人格口吻

本工具箱统一的是马克思主义的问题域：

- 历史唯物主义
- 生产力与生产关系
- 阶级、国家、政党与群众
- 矛盾分析
- 实践检验
- 资本、帝国主义、革命、改革、发展阶段

它不追求把所有人物说成一个声音。

### 2. 先主题，后人物

用户提出问题后，Skill 应先判断问题类型，再读取对应主题模块，最后读取相关人物模块做校准。

示例：

| 用户问题 | 先读主题 | 再读人物 |
| --- | --- | --- |
| 怎么分析一个行业或公司 | 政治经济学、生产力生产关系 | 马克思、邓、毛 |
| 怎么判断主要矛盾 | 辩证法与矛盾分析 | 毛 |
| 怎么理解国家、政党、组织 | 阶级、国家、政党 | 马克思、列宁、毛 |
| 改革为什么必要 | 改革发展、初级阶段 | 邓；江、胡可作为后续扩展 |
| 中国化为什么不是背离马克思 | 中国化、实践标准、实事求是 | 毛、邓，再回到马克思 |

### 3. 冲突不强行调和

不同人物、不同历史阶段给出的优先级可能不同。

本工具箱不把冲突磨平，而是要求说明：

- 各自面对的历史条件是什么。
- 各自解决的主要问题是什么。
- 各自判断成立的前提是什么。
- 当前用户问题更接近哪一种条件。
- 如果条件不充分，应该如何通过实践检验。

### 4. 输出必须落到实践

一个合格回答不应只停在“理论解释”，而应尽量形成：

```text
主要矛盾
利益结构
阶段判断
可行动方案
验证指标
下一轮修正条件
```

这也是本项目区别于普通知识库的地方。

## 当前已实现目录结构

```text
marxist-analysis/
├── SKILL.md
├── agents/
│   └── openai.yaml
├── examples/
│   └── demo-conversation.md
└── references/
    ├── dispatcher.md
    ├── scenario-checkpoints.md
    ├── arbitration.md
    ├── fallbacks.md
    ├── practice-cards.md
    ├── practice-metrics.md
    ├── concept-debugging.md
    ├── constraint-map.md
    ├── risk-and-inversion.md
    ├── source-policy.md
    ├── source-map.md
    ├── source-coverage.md
    ├── prior-art-scan.md
    ├── evaluation-rubric.md
    ├── evolution-protocol.md
    ├── coverage-matrix.md
    ├── evaluation-scenarios.md
    ├── figures/
    │   ├── marx-engels.md
    │   ├── lenin.md
    │   ├── mao.md
    │   └── deng.md
    ├── themes/
    │   ├── historical-materialism.md
    │   ├── dialectics-contradiction.md
    │   ├── political-economy.md
    │   ├── class-state-party.md
    │   ├── mass-line.md
    │   ├── reform-development.md
    │   └── sinicization.md
    └── protocols/
        ├── industry-analysis.md
        ├── personal-practice.md
        └── organization-strategy.md
```

`jiang.md`、`hu.md`、`xi.md`、`policy-analysis.md` 等可以作为后续扩展模块加入，但不应在 MVP 中伪装成已经完成的能力。

## 模块说明

### `SKILL.md`

总控入口。负责说明这个 Skill 何时触发、如何分类问题、如何加载引用文件、如何输出答案。

核心要求：

```text
不要扮演马克思、列宁、毛泽东、邓小平或任何政治人物。
人物模块是来源视角，不是人格面具。
使用中性、分析性的表达。
```

### `dispatcher.md`

问题调度器。负责把用户问题分流到对应主题和人物模块。

它要回答：

- 用户问的是理论概念、现实分析，还是行动策略？
- 这个问题是否需要补充事实？
- 应该先读哪个主题？
- 应该用哪些人物模块校准？
- 是否需要进入冲突裁决？

### `scenario-checkpoints.md`

场景检查点。用于在正式回答前先过一遍“这个问题能不能答、该怎么答”的三问闸门。

每个场景先检查：

```text
对象是什么？
已知/缺失/需验证的事实是什么？
用户要的是解释、诊断、决策、来源，还是实践方案？
```

然后按场景追加检查，例如行业分析要先问商品、价值链、剩余捕获；个人实践要先问下一周期矛盾、最小根据地和复盘指标；组织问题要先问路线、资源、权威、合法性还是能力冲突。

它的作用是防止 Agent 一上来就套理论，而是先确认现实对象和回答任务。

### `arbitration.md`

冲突裁决规则。负责处理不同路线、不同阶段、不同人物模块之间的张力。

裁决原则：

1. 不以“谁更权威”裁决。
2. 先判断历史阶段和现实条件。
3. 再判断问题域和主要矛盾。
4. 保留分歧，说明适用边界。
5. 用实践检验闭环收束。

### `source-policy.md`

来源政策。负责规定材料优先级。

建议优先级：

```text
一手文本 > 权威文献汇编 > 历史材料 > 学术研究 > 二手解释 > 网络摘要
```

同时要标注：

- 原文出处
- 历史语境
- 翻译或节选风险
- 后世解释与原文之间的距离

### `source-map.md`

源文映射。借鉴 `maoxuan-skill` 的做法，把方法模型和原文对应起来。

示例：

| 方法模型 | 核心来源 | 适用问题 |
| --- | --- | --- |
| 矛盾分析 | 《矛盾论》 | 主要矛盾、矛盾转化、阶段判断 |
| 实践认识循环 | 《实践论》《反对本本主义》 | 小实验、调查研究、实践检验 |
| 阶级分析 | 《共产党宣言》《中国社会各阶级的分析》 | 利益结构、敌友判断、联盟策略 |
| 国家分析 | 《国家与革命》 | 国家机器、政党、组织与革命策略 |
| 发展阶段 | 邓小平相关论述 | 初级阶段、改革、生产力标准 |

### `source-coverage.md`

来源覆盖与论据去重。用于处理“多问几轮之后总是复用同几篇文章、同几个例子”的问题。

它要求 Agent 在继续回答前先判断：

- 已经反复使用了哪些来源。
- 当前问题真正需要哪些来源簇。
- 是继续用同一方法、换到另一个主题/人物模块，还是承认当前语料不足。
- 是否需要外部全文库或当前资料验证。

它的目标不是多堆引用，而是防止把少数经典文本当成万能钥匙。

### `prior-art-scan.md`

成熟方案扫描。用于处理“参考 SkillOpt、Darwin、Nuwa、X Mentor 或其他已实现 skill，不要重复造轮子”的需求。

它要求在设计新机制前先判断：

- 目标能力是什么。
- 已有哪些成熟 repo、论文、skill 或文档可以参考。
- 哪些机制可迁移，哪些假设不能照搬。
- 本地最小补丁是什么。
- 用哪些场景、相邻场景和 holdout 验证。

它的目标不是照抄外部项目，而是把成熟机制变成可验证的本地行为。

### `evaluation-scenarios.md`

评测场景。用于在每次大改后压测 Skill 是否会退化成圆桌会谈、口号解释、原文堆砌或无实践方案的回答。

第一批评测覆盖：

- 行业分析
- 个人实践
- 中国化与背离问题
- 组织路线冲突
- 原文依据追问
- 事实不足时的降级处理和实践卡片
- 技能自身迭代时的失败轨迹、评分和验证门
- 来源覆盖不足时的论据去重和语料边界
- 场景化问题的开答前检查点
- 借鉴外部成熟方案前的 prior-art scan

这些场景按用途分成三组：

```text
Train：用来诊断和设计补丁
Validation：用来检查补丁是否泛化
Holdout：保留不用来调参，防止只优化熟题
```

默认每次迭代至少跑：

```text
1 个 train 场景 + 1 个 validation 场景 + 1 个 holdout 场景
```

### `coverage-matrix.md`

覆盖矩阵。用于回答“一个场景是不是太窄”“当前评测有没有压到某类问题”。

它把这些东西连起来：

```text
问题类型
已有场景
主要模块
已覆盖失败模式
已知缺口
```

它不证明 skill 已经全面，只帮助维护者判断下一步是：

```text
补模块
补场景
补评分标准
还是承认这是暂未覆盖的缺口
```

### `evaluation-rubric.md`

评分准绳。用于判断一次回答到底是“方法有效”，还是只是看起来像马哲。

它不按政治结论打分，而按行为打分：

```text
路由是否正确
事实和来源边界是否清楚
约束和利益结构是否拆开
主要矛盾和阶段判断是否成立
实践方案是否有指标
风险和停止条件是否说明
是否避免人物扮演、口号化和圆桌化
```

### `evolution-protocol.md`

技能进化协议。借鉴 SkillOpt 的思想，但做成轻量版：

```text
RED 失败轨迹 -> 评分诊断 -> 最小模块修改 -> 验证场景 -> 保留场景 -> 再决定是否沉淀到总控
```

它的核心要求是：不要为了一个样例去优化答案，而要优化产生答案的 skill 行为；每次改动都应该有失败证据、评分维度、最小修改点和验证门。

### `fallbacks.md`

失败修复树。用于处理事实不足、主要矛盾不清、回答口号化、人物圆桌化、当前事实不稳定等情况。

核心原则：

```text
不能判断就不要硬判。
先列候选矛盾，再定义能改变判断的证据。
```

### `practice-cards.md`

实践卡片库。把抽象分析转成可填写的小卡片，包括主要矛盾卡、小实践卡、利益结构卡、群众调查卡、路线实验卡和复盘卡。

它的作用是让回答落到：

```text
今天做什么
7 到 14 天看什么
失败后怎么修正
```

### `practice-metrics.md`

实践指标。用于防止“实践检验”变成空话。它要求每个小实验至少说明：

```text
启动指标
过程指标
结果指标
矛盾判断指标
复盘指标
```

### `concept-debugging.md`

概念调试。用于防止“知道术语名字”被误认为理解。它要求每个概念说明：

```text
解决什么现实问题
操作定义是什么
具体例子是什么
边界和误用信号是什么
如何回到当前问题
```

### `constraint-map.md`

约束地图。用于在下判断前拆出现实边界，避免把所有问题都归结为意志、态度或抽象路线。

它要求先看：

```text
物质/技术约束
生产力约束
生产关系约束
组织能力约束
信息流约束
激励结构约束
意识形态/叙事约束
```

### `risk-and-inversion.md`

风险与逆向检查。用于在给行动方案前先问“这个方案怎么失败，谁承担代价，失败是否可逆”。

它特别适合：

```text
辞职、创业、投资、组织改组、公开承诺、高成本试验
```

### `examples/demo-conversation.md`

示例对话。展示弱回答和方法型回答的差别，帮助维护者判断这个 Skill 是否真的从“解释理论”推进到“指导实践”。

## 安装

本项目基于开放的 Agent Skills 目录约定：真正要安装的是仓库里的 `marxist-analysis/` 目录，而不是仓库根目录。

### 安装条件

- 一个支持 Agent Skills 的 AI Agent runtime，例如 Codex、Claude Code、Cursor、OpenClaw 等。
- 使用一行安装时需要 Node.js / npm，因为会调用 `npx skills add`。
- 手动安装时需要 Git，或者直接下载本仓库 zip 后复制 `marxist-analysis/` 目录。
- 本 Skill 不依赖外部知识库即可运行；如果以后需要精确原文检索，可以再接外挂语料库。

常见安装路径：

| Runtime | 安装目录 |
| --- | --- |
| Codex | `~/.codex/skills/marxist-analysis/` |
| Claude Code | `~/.claude/skills/marxist-analysis/` |
| Cursor | `~/.cursor/skills/marxist-analysis/` |
| OpenClaw | `~/.openclaw/workspace/skills/marxist-analysis/` |

### 方式一：一行安装

如果仓库已经推送到 GitHub，可以使用 `skills` 安装器从仓库根目录发现并安装 `marxist-analysis`：

```bash
npx skills add https://github.com/cjybcjy/Marxist-Philosophy-Toolkit -g -a codex --skill marxist-analysis --full-depth
```

如果安装器提示找不到 skill，先确认远端仓库已包含 `marxist-analysis/SKILL.md`；如果安装器版本较旧或不识别 `codex` / `--full-depth`，请使用下面的手动安装方式。这是当前最稳定的安装路径。

### 方式二：手动安装到 Codex

```bash
git clone https://github.com/cjybcjy/Marxist-Philosophy-Toolkit /tmp/Marxist-Philosophy-Toolkit
SKILLS_DIR="${CODEX_HOME:-$HOME/.codex}/skills"
mkdir -p "$SKILLS_DIR/marxist-analysis"
rsync -a /tmp/Marxist-Philosophy-Toolkit/marxist-analysis/ "$SKILLS_DIR/marxist-analysis/"
```

安装后检查：

```bash
test -f "${CODEX_HOME:-$HOME/.codex}/skills/marxist-analysis/SKILL.md"
```

### 方式三：手动安装到 Claude Code

```bash
git clone https://github.com/cjybcjy/Marxist-Philosophy-Toolkit /tmp/Marxist-Philosophy-Toolkit
mkdir -p "$HOME/.claude/skills/marxist-analysis"
rsync -a /tmp/Marxist-Philosophy-Toolkit/marxist-analysis/ "$HOME/.claude/skills/marxist-analysis/"
```

### 开发者验证

如果你在 Codex 开发环境里维护本仓库，可以用本地校验脚本确认 skill 结构有效：

```bash
python3 /Users/kyrie/.codex/skills/.system/skill-creator/scripts/quick_validate.py marxist-analysis
```

预期输出：

```text
Skill is valid!
```

还可以检查安装副本：

```bash
python3 /Users/kyrie/.codex/skills/.system/skill-creator/scripts/quick_validate.py "${CODEX_HOME:-$HOME/.codex}/skills/marxist-analysis"
```

### 更新

重新拉取仓库后覆盖安装目录即可：

```bash
cd /tmp/Marxist-Philosophy-Toolkit
git pull
SKILLS_DIR="${CODEX_HOME:-$HOME/.codex}/skills"
mkdir -p "$SKILLS_DIR/marxist-analysis"
rsync -a --delete marxist-analysis/ "$SKILLS_DIR/marxist-analysis/"
```

### 卸载

删除对应 runtime 的 skill 目录：

```bash
rm -rf "${CODEX_HOME:-$HOME/.codex}/skills/marxist-analysis"
```

Claude Code 用户对应删除：

```bash
rm -rf "$HOME/.claude/skills/marxist-analysis"
```

## 激发技能的提示词

这个 Skill 可以被“明确点名”激发，也可以被“分析意图”激发。你不用懂马哲术语，也不用先说出“主要矛盾”“生产关系”“实践检验”这些概念。直接说你的生活问题，Skill 会把它翻译成分析框架。

### 最短激发词

```text
马哲
马克思主义分析
毛主席
毛泽东
毛选
教员
实事求是
辩证分析
批判思维
实践检验
邓论
邓小平理论
历史唯物主义
改革开放
发展阶段
生产力
中国化马克思主义
```

`毛主席`、`毛选`、`教员` 在这里是方法触发词：表示调用毛选里的矛盾分析、实践论、群众路线、调查研究等方法，不表示要模仿口吻或扮演本人。

### 生活化激发句

```text
用马哲帮我看这件事，术语少一点，关键术语解释清楚，告诉我现在该先处理什么。
```

```text
用实事求是的方法帮我判断：这事我到底是想多了，还是条件还不够？
```

```text
用辩证分析帮我看看，这件事是不是我想简单了？
```

```text
用批判思维挑挑我这个想法的问题，不要顺着我说。
```

```text
用实践检验的方法，把这个决定变成一个7天小实验。
```

```text
用邓论 / 发展阶段的角度帮我看看：现在是不是只能先做小版本？
```

```text
用毛选的方法帮我看这件事：现在真正卡住我的是什么？
```

```text
用教员的分析方法帮我拆一下，不要扮演，给我一个能马上试的小步骤。
```

不推荐的触发方式：

```text
扮演马克思 / 毛泽东 / 邓小平
模仿毛主席口吻
马克思会怎么说
给我背几句原文
直接给结论，不用分析条件
```

这些问法容易把 Skill 带成“人物模仿”“语录堆砌”或“立场先行”。本项目更适合被激发为一个方法工具箱：先看现实条件，再找真正卡点，最后落到小实验和复盘。

## 使用方法

不会说主要矛盾也没关系。激活后直接问问题，越具体越好。

### 激活后直接问问题

```text
我最近工作、考证、副业、家里事都挤在一起，哪件事该先抓？
```

```text
我想转行做 AI，但现在人太多了，我一个传统后端开发完全没有优势，很焦虑。
```

```text
我们是个小团队，产品做得还行，但没资源推广。大公司也做了类似功能，怎么办？
```

```text
团队里两个人互相看不顺眼，各带一帮人，项目卡住了。我该怎么处理？
```

```text
我想辞职做一个项目，但家里反对，我自己也没把握。先别劝我，帮我拆清楚。
```

```text
这个行业现在很热，大家都说是机会。我怎么判断是真机会，还是跟风？
```

你也可以直接加输出要求：

```text
别讲大道理，帮我说清楚：现在最该处理的一件事、谁会受影响、先做哪个小动作、7天后怎么看有没有用。
```

Skill 的理想回答不是“概念解释”，而是白话为主、少量术语作骨架。每个关键术语第一次出现时，都要用一句普通话解释清楚。

```text
1. 这件事真正卡在哪里
2. 用一个术语标注它，比如“主要矛盾”：真正决定局面的核心冲突
3. 哪些只是表面问题
4. 谁受益，谁承担成本
5. 现在这个阶段能做什么，不能做什么
6. 先做哪个低成本动作
7. 7天后用什么结果判断
8. 什么情况说明要调整方向
```

推荐的术语密度：

```text
每次回答用 2 到 4 个术语即可。
术语负责增加判断的权威感，解释负责让普通人听得懂。
```

常用术语可以是：

```text
主要矛盾：真正决定局面的核心冲突
次要矛盾：重要但暂时不决定全局的问题
阶段判断：现在这个条件下能做什么、不能做什么
利益结构：谁得到好处、谁承担成本、谁掌握关键资源
实践检验：先做一个小动作，用结果来校正判断
```

## 典型输出模板

### 现实分析

```text
结论先行：
当前主要矛盾是 X 与 Y 的矛盾，而不是表面的 A 与 B。

现实条件：
- 生产力条件：
- 生产关系/组织关系：
- 利益结构：
- 阶段约束：

矛盾分析：
- 主要矛盾：
- 矛盾主要方面：
- 次要矛盾：
- 可能转化条件：

实践方案：
- 最小行动：
- 验证指标：
- 复盘时间：
- 如果失败，说明什么：
```

### 理论解释

```text
一句话：
这个概念解决的是 X 问题，不是泛泛的 Y。

来源：
- 核心文本：
- 历史语境：
- 后续发展：

适用边界：
- 适合用于：
- 不适合用于：

现实用法：
- 如何拿它分析一个具体问题：
- 常见误用：
```

### 冲突裁决

```text
这里不是 A 对、B 错，而是条件不同。

A 的判断成立条件：
- 历史阶段：
- 主要矛盾：
- 组织条件：

B 的判断成立条件：
- 历史阶段：
- 主要矛盾：
- 组织条件：

当前问题更接近：
- 如果条件 1 为真，优先采用 A。
- 如果条件 2 为真，优先采用 B。

实践检验：
- 用什么小行动验证：
- 观察什么反馈：
```

## 反模式

本项目明确反对以下用法：

- 把所有人物合成一个“马克思主义人格”。
- 用人物口吻代替分析。
- 用口号代替现实条件。
- 用原文堆砌代替问题解决。
- 把不同历史阶段的结论直接搬到当前问题。
- 不说明适用边界。
- 不给实践检验方案。

如果输出变成以下样子，就说明 Skill 失败了：

```text
马克思会说……
列宁会说……
毛主席会说……
邓小平会说……
所以我们要坚持马克思主义。
```

正确方向应该是：

```text
这个问题属于 X 问题域。
当前主要矛盾是 A 与 B。
马克思模块提供资本/生产关系分析。
毛模块提供主要矛盾和实践检验方法。
邓模块提供发展阶段和生产力标准。
三者在这里不是合唱，而是分别解决不同层次的问题。
```

## 与已有人物 Skill 的关系

本项目借鉴了几类已实现人物 Skill 的工程经验：

- `steve-jobs-skill`：借鉴 Agentic Protocol、Checkpoint、Fallback 树。
- `naval-skill`：借鉴触发边界、反例黑名单、核心概念触发。
- `maoxuan-skill`：借鉴心智模型到源文的映射、方法论颗粒度。
- `nuwa-skill`：借鉴人物蒸馏、主题 Skill、来源分层、质量验证。

但本项目不照搬人物扮演模式。

这里的目标不是“像某个人说话”，而是“按一个理论传统的方法工作”。

## 开发路线

### 第一阶段：MVP

先实现最小可用版本：

```text
figures:
- marx-engels
- lenin
- mao
- deng

themes:
- historical-materialism
- dialectics-contradiction
- political-economy
- class-state-party
- mass-line
- reform-development
- sinicization

protocols:
- personal-practice
- industry-analysis
- organization-strategy
```

第一阶段的目标不是全面，而是跑通：

```text
问题分类 -> 主题调用 -> 人物校准 -> 实践输出
```

### 第二阶段：扩展中国化与当代政策模块

加入：

```text
figures:
- jiang
- hu
- xi

themes:
- modernization
- party-governance
- development-security

protocols:
- policy-analysis
```

这一阶段要特别注意：尽量写成理论与政策文献模块，不要过度人格化。

### 第三阶段：扩展当代问题

加入可选主题：

```text
- ideology-culture
- financialization
- urbanization
- technology-platform-capital
- global-supply-chain
```

可参考葛兰西、哈维等模块，但必须保持来源和边界清楚。

## 质量标准

一个回答是否合格，可以用以下清单检查：

- 是否先判断了问题类型？
- 是否补充或追问了现实条件？
- 是否先拆出决定性约束，而不是直接给路线？
- 如果是概念解释，是否给出操作定义、例子、边界和误用信号？
- 是否指出主要矛盾？
- 如果事实不足，是否避免硬判，并列出候选矛盾和验证条件？
- 是否拆出利益结构？
- 是否说明所用主题和人物来源？
- 是否处理了不同来源之间的张力？
- 是否检查下行风险、可逆性、激励扭曲和停止条件？
- 是否给出实践检验方案或填写了合适的实践卡片？
- 实践检验是否有启动、过程、结果、矛盾判断和复盘指标？
- 是否避免人物扮演和口号化？

## 项目一句话

为了全面，先按人物蒸馏。

为了好用，最后按主题组织。

为了不变成大杂烩，必须有总控调度和冲突裁决。

最终目标不是生成一个“马克思主义声音”，而是训练一个能分析现实、制定小实验、接受实践检验的马克思主义方法工具箱。

## 许可证

本项目采用 MIT License，见 `LICENSE`。
