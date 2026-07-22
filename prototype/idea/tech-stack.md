# 技术选型

> 游戏开发的技术栈选择。框架级定义。

---

## 游戏引擎：Godot 4（最新稳定版）

### 选择理由

| 考量 | 结论 |
|---|---|
| 项目规模 | 2D 卡牌 + 文本叙事，Godot 能力远超需求 |
| 类型安全 | Godot 4 支持 typed Dictionary/Array + Strict Mode，解决运行时类型错误 |
| AI 友好度 | GDScript 语法简洁，AI 生成质量高，符合"AI写代码、人提供创意"的协作模式 |
| 成本 | 开源免费，无商业授权问题 |
| 长期维护 | Godot 4 是主力开发分支，社区活跃 |

### 版本策略

- 使用 Godot 4.x 最新稳定版
- 开发中途不追新版本，等开发告一段落再考虑升级

---

## 语言：GDScript（静态类型）

开启 Strict Mode，所有变量和函数签名做类型标注：

```gdscript
var card_name: String = ""
var relationship_value: int = 0
var npc_trust: Dictionary[String, int] = {}
```

---

## 架构：逻辑与表现分离

```
res://
├── core/           # 纯逻辑，不依赖 Godot 场景树
│   ├── game_state.gd
│   ├── card_system.gd
│   ├── relationship_system.gd
│   ├── resource_system.gd
│   └── event_resolver.gd
├── scenes/         # 表现层，只负责展示和交互
│   ├── card_ui.gd
│   ├── npc_panel.gd
│   └── event_scene.gd
└── data/           # 数据驱动
    ├── cards.json
    ├── events.json
    └── npcs.json
```

核心逻辑层（`core/`）不继承 Node，不依赖场景树，可脱离 Godot 运行环境单独测试。

---

## 质量保障：分层防御

| 防御层 | 解决什么问题 | 成本 |
|---|---|---|
| 静态类型 + Strict Mode | 类型错误、拼写错误 | 低 |
| 逻辑与表现分离 | 核心逻辑可独立测试 | 中 |
| 单元测试（GUT） | 逻辑错误、数值错误 | 中 |
| 数据校验 | 配置错误、缺失字段 | 低 |

### 测试框架：GUT（Godot Unit Test）

核心系统（关系值计算、资源结算、事件触发、属性检定）全部用测试覆盖。

---

## 数据格式

- 卡牌、事件、NPC 数据：JSON
- 叙事文本/对话：待确定（可能是 JSON 或专门的叙事格式）
- 加载时做字段校验，数据错误在加载时报错

---

## 待确定

- 叙事文本的存储格式（JSON vs Ink vs Yarn Spinner vs 自定义）
- 存档系统的实现方式
- 是否需要版本管理工具协作叙事内容
- 目标平台的打包配置（Windows/Mac/Linux）

---

## 关联文档

- [游戏整体定位](./overview.md)
- [核心机制](./core-mechanics.md)
- [UI/UX 方向](./ui-ux.md)
- [音频方向](./audio-direction.md)
- [未决事项](./open-questions.md)
