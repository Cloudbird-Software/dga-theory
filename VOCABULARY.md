# VOCABULARY —— DGA 词汇 ↔ 实施层对应物归并表

> IR-0009 卡 A4（依据 ADR-0107 层级声明）。每行三列：DGA 词汇 / 实施层对应物 / 归并裁决。
> 归并裁决取值：`同一物`（字面对应）｜`同构`（机制语义等价）｜`同构且更严`｜`部分`（有承载有缺口）｜`flag-实例缺`（理论有条款实例无承载→补缺候选）｜`flag-理论缺`（实例有机制理论无条款→理论审议材料）。
> 校验方式：每行对照现行文件正本（宪法 v2.4 / GOVERNANCE.yaml / policy/ / ADR 序列）；`flag` 行单独分流（见文末）。

| # | DGA 词汇 | 实施层对应物 | 归并裁决与注记 |
|---|---|---|---|
| 1 | 闭环单元（六元组） | IR→spec→卡→PR→验收 流水线；卡 schema 的 budget/capabilities/evidence 三块 | 同构。卡三块=六元组的宪法投影（IR-0006 W2-C3，宪法 §14b） |
| 2 | 意图登记 | IR issue（intent.yml 模板九字段，IFACE-01） | 同一物 |
| 3 | 裁决层（S5） | owner（randypanding） | 同一物；STRAT §2.2 独占清单=宪法 §0 判断工作条款 |
| 4 | 执行层（S1） | PM 会话 + CNB 池扇出 + cloudbrid-agent App | 同构（ADR-0085 PM 范式） |
| 5 | 判定闭环（S3） | arbiter（零 LLM/默认拒绝/CAS）+ eval-gate（零 LLM）+ verifier T2（veto-only） | 同构且更严（INV-01/02；判定物有效性自检超 DGA 目标） |
| 6 | S4 扫描 | patrol（三源）+ drift-check（小时级）+ cnb-audit + canary-sweep + CodeQL/dependabot | 同构；生态/方法/前沿资产化=卡 C2 |
| 7 | 资源池调度闭环（S2） | conductor + cnb-dispatch + cost-check（预算四元组硬停三件套） | 同构 |
| 8 | 记忆层 | archive 仓（ADR 正本+evidence 账本+runs+retired 快照） | 同一物（宪法 §1） |
| 9 | 自治阶梯 L0–L5 | 硬谓词白名单 fail-closed + shadow 域解锁（≥50 例一致零逃逸） | 同构：域解锁=声明的晋升流程（宪法 §5） |
| 10 | 波次 | IR 内 wave / 卡批次（wave_schema.py） | 词汇归并：以"波次"指 IR 内批次（FR-04 裁决） |
| 11 | holdout（隐匿判定集） | holdout 仓 sealed 场景（HO-0001~0010，sealed_sha256 引用纪律） | 同一物；v1.1 后答案层迁 CNB 私有阵地（FR-01） |
| 12 | 判定基准的隐匿部分 | golden 断言+判分逻辑（迁 CNB）；canary 泄漏诱饵 | 同构（N-5）；诱饵+公开面扫描=DGA v1.1 其二·附执法面 |
| 13 | 外部真值锚 | verifier-exam（RewardBench2+LLMBar+null canaries，ADR-0072） | 同构且更严（入职考试+校准+标注负债申报） |
| 14 | 对齐物（oracle） | eval-quad 四元组 pin（id@sha8）+ CIW 钉版下发 | 同构；版本链显式存档=登记规范缺（补缺件） |
| 15 | spec（规格） | 条款级 spec + 测试设计 + AC（OpenSpec/StrictDoc/EARS 范式，宪法 §9#1 署名） | 同一物 |
| 16 | eval 三层（可见/隐匿/外部锚） | holdout 轮换池 + evalsets + verifier-exam | 同构（STRAT v1.1 §5.2 表） |
| 17 | 三重度量（分歧/还原/时代性） | 语义熵分歧聚簇（ADR-0066）/ eval-gate 非劣性+holdout_gap（pending）/ recency_coverage（blocked） | 部分；时代性=flag-实例缺（C3 激活条件已登记） |
| 18 | 判例库 | ADR 墓碑索引 + conformance 32 卡语料 + promotions 账本 + 误放行台账 | 同构 |
| 19 | 负结果库 | 散在 ADR/REMOVAL/cannot-reproduce 三值判定 | **flag-实例缺**→卡 C1 建设（NEG schema 已备） |
| 20 | 研究闭环 | IR 探索段 + patrol 前沿源 + 红队对抗研究 | 部分：短时距/低预算/二元产出参数化缺（MIG W5 残余） |
| 21 | 前沿资产（能力前沿快照） | （无版本化快照；verifier-exam 结果+切换 ADR 为原料） | **flag-实例缺**→卡 C2 建设 |
| 22 | 验证比 | 注意力会计（签署耗时/可疑快速签/needs-human p90/每合并 owner 分钟） | 同构且更严（metrics.yaml；自动化超前 MIG §5.1 排序） |
| 23 | 外部对齐度 | verifier-exam 外部基准通过率 + holdout_gap 护栏位（数据源 pending） | 部分（数据源建设=metrics.yaml pending 项） |
| 24 | 爆炸半径 | （无显式度量；依赖图分析待做） | **flag-实例缺**：可分解为 App 挂载面×镜像新鲜度×端点冗余三读数（候选补缺） |
| 25 | 闭环延迟/自治时距/升级率 | conductor 时间戳+事件流+butler-ledger+evidence-query 七源 | 同构 |
| 26 | 信息梯度三区 | 三阵地（GitHub 公开/CNB 私有/CNB+Gitee 镜像）+ 证据账本三层 | 同构（STRAT v1.1 §4.1）；三不变量=INV-04/06+DECISION-02 |
| 27 | 数据分级 D-公开/内部/客户敏感 | trust_level + data_classes_allowed（FR-08 修订，IR-0010 卡 B1 落地）+ tenant 字段 | 部分：D-内部随阵地诞生为现实类；D-客户敏感挂宪法触发器 |
| 28 | 端点信任级 E1/E2/E3 | providers.yaml trust_level 字段 + 判定链唯一 LLM 通道（llm-verifier） | 同构（T-05 登记建议落地中） |
| 29 | 升级矩阵（A-23） | needs-human + 决策卡三选项（"都不对"附反例）+ elevation.py | 同构且更严（第三选项=分歧申报的结构化） |
| 30 | 规格沉默/裁量登记 | PM 阶段内自主 + 红线边界（判定语义/fail-closed/append-only/凭据） | 部分：裁量登记义务=A5 增量并线（块 1）补齐 |
| 31 | 分歧申报（A-51） | 语义熵分歧+红队 survived+运行报告体感节 | 部分：禁"向共识收敛"明文=A5 增量（块 2）+AGENTS.md N-8 行补齐 |
| 32 | 判例援引（A-41） | ADR 引用纪律（C1 路径 PR 必引 ADR-NNNN） | 部分：判定前检索义务=A5 增量（块 4）补齐 |
| 33 | 负结果查询（A-40） | （无查询义务；库未建） | **flag-实例缺**→C1+块 3 补齐 |
| 34 | 责任终点（具名的人） | owner merge/签署（宪法 §0：LLM 永无 approve/合并权） | 同一物 |
| 35 | 断裂登记簿 | archive/fractures/LEDGER（卡 A7 开通）+ ADR 墓碑 + GM 元治理 | 同构（DGA 语义自 A7 起生效） |
| 36 | 自举核 | 人工直管残余面（宪法 §10.2：2-3h/周判断预算） | 同构：A2 absorption 后按 MIG §3.1 判据正式重估登记 |
| 37 | 狗粮公示 | 全仓公开+dashboard+飞书投影+SLI 周报+runs 周报 | 同构且强于预期（从第一天全公开） |
| 38 | 判定/执行分离 | arbiter 独立于 butler（拆家原则）+ LLM 无 approve + verifier-app 写权分离 | 同构且更严 |
| 39 | 凭证方向性（DGA §5.8 其三） | INV-04（key 只存 org secret/Vault；零凭据上下文）+ App 单仓短令牌 | 同构且更严 |
| 40 | 成本熔断 | cost-check 波次通道（usd/tokens/wallclock/human_minutes 硬停三件套，run 33245465018 实弹） | 同构 |

## flag 分流清单

**flag-实例缺（补缺候选，进入 IR-0009/0010 卡）**：
- #19 负结果库 → 卡 C1（schema+NEG-0001+复活钩子）
- #21 前沿快照 → 卡 C2（FRONTIER-SNAPSHOT v1+失败分类）
- #17 时代性 → 卡 C3（blocked，holdout_gap 数据源激活）
- #33 负结果查询义务 → 卡 A5 块 3（ROLE-IMPLEMENT）
- #24 爆炸半径 → 候选补缺（未立项，待月度理论审议分流）

**flag-理论缺（理论审议材料，交月度审议）**：
- 宪法 §7 反退化设计（owner 独立复算/每周亲手一件/决策卡第三选项）——DGA 无对应条款
- 宪法 §6 外部 dead-man 心跳（缺席即停的"缺席"如何被外部感知）——DGA-A N-7 有停语义、无外部时钟条款
- 宪法 §4A 棘轮（全仓指标只许变好）——DGA 无治理指标单调性条款
-宪法 §12 label 唯一真源（投影漂移以真源为准并告警）——DGA §5.8 有单向梯度、无"投影纪律"明文

## 校验记录

- 行数：40 ≥ 25（门禁）✓
- 抽查 5 行 owner 核对：**待 owner**（S 点之外的低风险核对项，随收口一并送审）
- 每行对应物均在现行正本中验真（宪法 v2.4 / GOVERNANCE.yaml / policy/ 11 件 / ADR-0001~0106 / metrics.yaml / transitions.yaml）
