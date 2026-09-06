# dga-theory —— DGA 理论层 SSOT

> 层：理论层（ADR-0107 层级声明）｜ org: Cloudbird-Software ｜ 建仓：IR-0009 卡 A1（owner 委托执行，bootstrap 直推 (b) 类豁免——ADR-0109 决策 2）

## 文档族总表

| 文档 | 层 | 性质 | 现行版本 | 状态 |
|---|---|---|---|---|
| DGA（理论母版·人类版） | 理论 | 公理、定律、原语、形态学推导 | v1.0.1 | **原文缺件**——P-1~P-4 补丁待原文应用（见下） |
| DGA-A（agent 投影） | 理论 | 规范与判定条款 | v1.0 | 在位（FR-05：以增量并线方式装载，不整文灌入） |
| DGA-STRATEGY | 实例·策略 | 理论在本组织参数下的采样 | **v1.1**（补丁单 S-P-1~S-P-12 已应用） | 在位 |
| DGA-MIGRATION | 实例·路径 | 方法论备忘（v1.1 降级，FR-04） | **v1.1**（补丁单 M-P-1~M-P-5 已应用） | 在位 |
| DGA-TOOLING | 实例·任务 | 选型调研任务定义 | v1.0 | 在位（任务已返回归档，裁决由 ADJUDICATION 承接） |

配套裁决文件：DGA-ADJUDICATION v1.0（owner 2026-09-06，八断裂 FR-01~08 的约束性裁决）——正本入 archive/adr 上层由 IR-0009 A1 归档，本文档族以其为最高裁决依据。

## 缺件声明（诚实清单）

1. **DGA 理论母版（人类版）v1.0.1 原文不在交接包内**。交接包核对（HANDOVER D0-2）发现五份原文仅四份在位；按"缺件 → 停，不得凭记忆重建"纪律：
   - `patches/DGA-v1.0.1-to-v1.1.patch.md`（P-1~P-4：其二·附威胁模型分层 / 其四判定活性自检 / §1.7 预测观测登记 / 版本记录）**挂起未应用**；
   - absorption map 中 DGA 母版侧锚点标注「v1.1 待应用」；
   - **owner 动作**：提供 DGA 人类版 v1.0.1 原文一份 → 应用补丁 → DGA v1.1 诞生（补丁单已备，应用纪律见 patches/ 内文）。
2. DGA-ADJUDICATION 在 Downloads 交付件中的原件（`DGA-adjudiction.md`）待 owner 确认后入 `archive/adr/` 上层目录归档（append-only）。

## 目录结构

```
DGA-A-v1.0.md / DGA-STRATEGY-v1.0.md / DGA-MIGRATION-v1.0.md / DGA-TOOLING-v1.0.md   # 原文（v1.0 正本，git 历史即存档）
DGA-STRATEGY-v1.1.md / DGA-MIGRATION-v1.1.md                                          # 补丁应用后（v1.1 正本）
patches/                                                                               # 补丁单原件（版本演化证据链，永久保留）
VOCABULARY.md                                                                          # 词汇归并表（IR-0009 卡 A4）
absorption-map/                                                                        # 实施层→理论层映射（IR-0009 卡 A2，schema 见其 INDEX）
```

## 版本纪律

版本号递增、理由记录、禁止静默修改（STRAT 前言）。v1.0 原文以 git 历史为存档；补丁单 diff 即版本演化证据链。理论升版后，实例层文档在一波次内完成回链校对（断裂判据的实例化运行）。
