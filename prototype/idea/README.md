# AnimalFarm 游戏设计文档

> 基于《动物庄园》的叙事驱动策略卡牌游戏

## 文档索引

| 文档 | 内容 | 状态 |
|---|---|---|
| [overview.md](./overview.md) | 游戏整体定位、核心概念、精神内核 | ✅ 框架完成 |
| [story-prototypes.md](./story-prototypes.md) | 三个故事原型的对比与选择 | ✅ 框架完成 |
| [world-building.md](./world-building.md) | 世界观、玩家身份、时间框架 | ✅ 框架完成 |
| [narrative-design.md](./narrative-design.md) | 叙事结构、故事线、NPC弧、事件分层 | ✅ 框架完成 |
| [core-mechanics.md](./core-mechanics.md) | 回合制、卡牌、属性、关系、资源、审查、季节 | ✅ 框架完成 |
| [drive-and-endings.md](./drive-and-endings.md) | 四层驱动系统、结局系统 | ✅ 框架完成 |
| [art-direction.md](./art-direction.md) | 美术方向：视觉风格、色彩、角色、卡牌视觉 | ✅ 框架完成 |
| [ui-ux.md](./ui-ux.md) | UI/UX 方向：信息呈现、卡牌交互、NPC交互 | ✅ 框架完成 |
| [audio-direction.md](./audio-direction.md) | 音频方向：音乐风格、音效设计原则 | ✅ 框架完成 |
| [tech-stack.md](./tech-stack.md) | 技术选型：Godot 4 + GDScript + 数据驱动 | ✅ 框架完成 |
| [next-steps.md](./next-steps.md) | 后续讨论清单：20项待办，按优先级排列 | 📋 待推进 |
| [open-questions.md](./open-questions.md) | 未决事项、备选方向、未展开的想法 | 📝 持续更新 |

## 交叉引用说明

每个文档在涉及其他模块的内容时，使用 `[→ 参见 xxx.md]` 标注引用关系。
各文档可独立拓展，不影响其他模块的结构。

## 当前阶段

**原型设计阶段** — 所有方向的基本框架已确定，待深入拓展具体内容。

详见 [next-steps.md](./next-steps.md) 获取完整的后续讨论清单。

## 设计原则

- 机制决定高度，叙事决定深度
- 碎片化叙事，但所有细节可推导还原
- 玩法即信息（ludonarrative harmony）
- 做减法，不做加法——每个系统必须服务于核心体验
