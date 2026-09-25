# cybernetic-project-management

基于钱学森、宋健《**工程控制论**（上、下册）》蒸馏的**项目管理技能**——把控制论的反馈回路、稳定性、最优控制、协调、容错与大系统理论，转译为软件/工程项目的计划、监控与治理方法。

由 cangjie-skill（RIA-TV++ 流水线）蒸馏产出：5 个并行提取器扫描全书 21 章（187 万字）→ 三重验证 → 13 个原子能力 → 触发盲测 10/10 + 实际输出评测通过。

## 它能做什么（13 个能力）

| 能力 | 一句话规则 | 原书依据 |
|---|---|---|
| stability-health-check | 先判关键回路是否发散（一票否决），再量距失控边界的裕度 | 1.1/1.7/5.1 |
| multi-objective-tradeoff | 指标分别评价后抓当前主要矛盾；拒绝加权总分，保帕累托集 | 1.7/21.8 |
| feedback-cadence-design | 闭环三要素缺一不可；连续 N 次确认才升级、M 次正常才解除 | 17.1/10.6 |
| model-approximation-identification | 简化必须带边界声明；资源上限显式化；实测优先于理论 | 1.4–1.6 |
| noise-filtering-estimation | 平滑窗口取折衷；与噪声叠接的频段原理上不可分辨 | 15.1 |
| baseline-variance-control | 标准弹道+偏差摄动：基线不轻动、纠偏天天做、超域重定 | 第 13 章 |
| extremum-seeking-iteration | 用连续测量代替预先了解；节奏快过漂移慢过噪声；0.618 优选 | 第 16 章 |
| delay-compensation | 净偏差=表观偏差−在途动作；按最坏延迟设计仍收敛的纠偏 | 第 11 章 |
| decoupling-coordination | 有害耦合切断、有益耦合保留；解耦只落在接口层 | 第 6 章 |
| time-optimal-switching | 受限资源下最快=全力冲刺+准时切换；先问最优是否存在；终点补稳 | 8/9 章 |
| redundancy-fault-tolerance | 串联成功率=乘积先找瓶颈；热备/冷备/k-N 表决；容错能力=N−k | 第 19 章 |
| adaptive-self-stabilization | 红线触线即切换候选方案；盲试成功率 1/2ⁿ，先分组；改进须使偏差缩小 | 第 18 章 |
| large-system-decomposition | 分层是信息结构必然；切断独立设计再分析耦合；局部最优必须配全局协调 | 第 21 章 |

## 安装

```bash
git clone https://github.com/Fen9pi-Max/cybernetic-project-management.git
# ZCode / Claude Code 用户级安装
cp -R cybernetic-project-management ~/.zcode/skills/cybernetic-project-management   # 或 ~/.claude/skills/
```

技能为单入口模式：宿主 agent 读 `SKILL.md` 的路由表，按用户意图加载 1 张能力卡执行。每张能力卡含 R（原文依据）/ I（解释）/ A1（案例）/ A2（触发情境）/ E（执行步骤与输入输出契约）/ B（边界与原书警告）六段。

## 仓库结构

```
SKILL.md                    # 技能入口（路由表+核心原则+边界）
references/capabilities/    # 13 张能力卡
references/{cheatsheet,glossary,overview,capability-index}.md
test-prompts.json           # 触发测试用例（darwin 兼容）
test-results.md             # 盲测与输出评测记录
distillation/               # 蒸馏审计材料（可选阅读）
  BOOK_OVERVIEW.md          # 阶段0 整书理解
  verified.md               # 三重验证记录
  coverage-audit.md         # 15 项关键任务覆盖审计
  candidates/               # 5 个提取器的原始候选池
  GLOSSARY.md               # 39 条术语词典（含项目管理翻译）
  DIGEST.md                 # 面向读者的精华导读
```

## 边界

- 管理可观测、可纠偏的执行过程；不替代目标设定与人的判断
- 不适用于无任何执行数据的纯概念阶段、个人时间管理、具体工具操作

## 出处

- 原书：钱学森、宋健《工程控制论（上、下册）》，科学出版社
- 蒸馏流水线：cangjie-skill v2.5.0（RIA-TV++）
- 能力卡中的原书引文仅作方法论溯源（每段 ≤150 字），完整内容请阅读原书
