[English](README.md) | **简体中文**

# Paperpowers

Paperpowers 是一个面向 coding agents 的科研工作流系统。

它希望在 `AI/CS 实证研究` 中扮演类似 `superpowers` 在软件开发中的角色：通过初始指令、可复用 skills 和固定 workflow，让 agent 更像一个严谨的科研合作者，而不是一个执行很快但研究判断松散的助手。

## 它是什么

Paperpowers 主要面向：

- 问题定义与方向收敛
- 文献 grounding
- 假设形成与最小验证
- 论文规划与写作
- rebuttal 准备
- 科研结论与 claim 验证

## 它不是什么

在当前 scaffold 阶段，Paperpowers 还不是：

- 完整的实验调度平台
- GPU 编排系统
- benchmark dashboard
- 面向所有学科的一般学术助手

当前版本优先构建的是研究判断、流程纪律和论文导向的工作流。

## 长期目标

Paperpowers 的目标不只是当前这个 docs + skills scaffold，而是逐步发展成一层更完整的科研工作流系统。

长期目标包括：

- 更严谨的 idea shaping 和 literature grounding
- 在投入大规模算力之前先做最低成本验证
- 论文规划、写作与 rebuttal 支持
- 实验执行、监控与结果分析
- 把研究判断和经验验证更紧密地连接起来

实验层现在还没有实现。这是刻意的取舍。项目当前优先构建的是研究判断和论文侧 workflow，等核心工作流稳定后，再往实验操作层扩展。

## 核心工作流

当前设想的 V1 workflow 是：

`problem framing -> literature grounding -> hypothesis shaping -> quick validation plan -> direction decision -> paper plan -> section drafting -> evidence checking -> rebuttal prep`

## 当前 Scaffold 内容

当前仓库已经包含：

- Codex 集成文件
- 核心 philosophy 和 workflow 文档
- 9 个基础 skills：
  - `using-paperpowers`
  - `research-brainstorming`
  - `literature-grounding`
  - `hypothesis-to-validation`
  - `paper-planning`
  - `paper-writing`
  - `rebuttal-prep`
  - `research-verification`
  - `writing-skills`

## 计划中的 V1 Skills

- `using-paperpowers`
- `research-brainstorming`
- `literature-grounding`
- `hypothesis-to-validation`
- `paper-planning`
- `paper-writing`
- `rebuttal-prep`
- `research-verification`
- `writing-skills`

## 安装

如果你在 Codex 中使用，请参考 [`.codex/INSTALL.md`](.codex/INSTALL.md)。

## Philosophy

Paperpowers 的核心倾向是：

- evidence 优先于感觉
- 先把方向做对，再考虑实现规模
- 先做最低成本 falsification，再扩大实验
- 先把 narrative 结构理顺，再追求 prose polish
- 明确 claim 风险，而不是模糊乐观

### 我的设计哲学

这个项目还承载了一套更个人化的科研 ideation 与 literature 设计哲学。

第一，头脑风暴不只是“找论文”。文献综述当然重要，但思维方式同样重要。这个方向的一部分参考来自 [Orchestra Research 的 AI-Research-SKILLs](https://github.com/Orchestra-Research/AI-Research-SKILLs/tree/main/21-research-ideation)，尤其是其中 `brainstorming-research-ideas` 和 `creative-thinking-for-research` 的区分。

第二，未来的 brainstorming 不应该只有一种泛化模式，而应该按场景拆分。不同情境下，对发散、收敛、可行性和 literature depth 的要求都不一样。比如：

- **在拥挤领域里寻找范式级突破**：当某个方向已经进入“继续卷最后 1%-2% 精度”的阶段时，系统应该更偏向发散思维、范式切换和新角度探索。这类模式更接近 `creative-thinking-for-research`。
- **收敛且可落地的方案形成**：当目标是得到一个真实可执行、可论证、可实现的方案时，系统应该更偏向 narrowing、decision-making 和实际研究设计。这类模式更接近 `brainstorming-research-ideas`。
- **给学生准备稳妥方向**：有时目标并不是最激进的 idea，而是一组稳妥、适合学生执行、风险较低的研究题目。
- **做可行性讨论**：有时用户真正需要的并不是一个最终可行 idea，而是为组会汇报、proposal 讨论或和老板讨论研究计划可行性准备材料。

第三，不同场景对 brainstorming 和 literature grounding 的需求强度应该不同。有的场景需要先大范围探索，再慢慢收敛；有的场景则应该快速收敛，只保留最低必要的 literature map。工作流应该自适应，而不是把同一套 ideation 深度强行套到所有情况上。

第四，个性化很重要。理想情况下，系统在做 brainstorming 和 literature search 之前，应该能理解研究者自己的历史和偏好。未来版本希望能从一个本地文件夹中读取并加权：

- 研究者自己发表过的论文
- 研究者认真读过、重点关注过的论文
- 研究者感兴趣的论文

这套个人论文库应该影响搜索和 grounding 的优先级。此外，venue 质量也应该进入权重：除非任务明确要求关注前沿 preprints，否则顶会论文通常应比未审稿的 arXiv 论文获得更高搜索优先级。

这套哲学是 `paperpowers` 后续演进的设计目标，目前还没有在 scaffold 中完整实现，但它定义了这个项目希望成长的方向。

更多可见 [`docs/philosophy.md`](docs/philosophy.md) 和 [`docs/workflows/v1.md`](docs/workflows/v1.md)。

## 仓库结构

```text
paperpowers/
├── .codex/
├── docs/
├── examples/
└── skills/
```

## 当前状态

当前仓库仍处在 scaffold 阶段，但已经覆盖了 `paperpowers` 的完整 V1 skill surface，包括：方向形成、文献 grounding、最低成本验证规划、论文规划、章节草拟、rebuttal 准备、科研结论验证，以及内部 skill 演进能力。

## 贡献方式

如果你想贡献：

1. 最好从一个 issue、discussion 或清晰范围的 proposal 开始。
2. 对于较大的改动，先在 `docs/paperpowers/specs/` 中补设计说明，再在 `docs/paperpowers/plans/` 中补实现计划，然后再做实现。
3. skill 要保持紧凑、易触发、面向 workflow。`description` 应该说明“什么时候该用”，而不是把整个流程复述一遍。
4. 提交前请先做验证。对 skill 来说，至少确认关键标题、触发条件和输出约束存在；对文档来说，要确保 `README.md` 和仓库实际状态一致。
5. 尽量提交聚焦的 PR。一个小 skill、一个文档完善，或者一个 workflow refinement，都会比一个大杂烩式改动更容易 review。

适合作为 first contribution 的方向包括：

- 完善 examples
- 优化已有 skills 的 trigger wording
- 补充缺失的 workflow 文档
- 收紧 verification 规则
- 用具体、分阶段的方式推进未来 experiment layer 的设计
