# 壹原理科技 网站文案多样化修改方案

> 生成日期：2026-07-25  
> 适用范围：全站页面（首页、关于我们、产品中心、制造与服务、联系我们）  
> 语言：中文 + English（双语同步修改）  
> **注意：所有页面的 Hero 区（顶部标题区）保持现有文案不变。**

---

## 一、问题总览

通过对全站 5 大页面（含子页面）、15 个组件文件和 `site.ts` 数据源的逐段对比，识别出以下 **6 类核心重复问题**：

| 编号 | 重复类型 | 涉及位置 | 重复次数 |
|------|----------|----------|----------|
| R1 | "PCBA 制造与成品组装" 企业定位句 | 首页Hero、关于-公司简介、site.ts | **6+ 次** |
| R2 | 四类产品方向描述 | 首页产品区、关于-业务、产品中心、site.ts（business/detail/scenarios） | **5+ 次** |
| R3 | "打样→试产→量产→出货" 流程 | 首页Support、制造-生产、关于-合作路径、site.ts（production） | **4+ 次** |
| R4 | "三城协同" 布局描述 | 首页Footprint、关于-公司、联系-info、site.ts | **4+ 次** |
| R5 | "四个阶段/节点/原则" 模板化标题 | 制造-生产、制造-工艺、关于-文化、首页Support | **5+ 次** |
| R6 | "不卖标准品 / No off-the-shelf" | site.ts（business/detail）、产品中心、关于-公司 | **3+ 次** |

**核心结论**：同一信息在不同页面以几乎相同的措辞重复出现，用户浏览多页面时会感到审美疲劳，搜索引擎也会因为内容重复降低收录权重。需要为每个页面赋予**差异化的信息角度和表达方式**。

---

## 二、分页面修改方案

### 【首页 Home】— 定位：品牌第一印象，展示"广度"

首页应突出**整体品牌调性**和**能力概览**，用一句话建立信任，避免与内页共享相同的细节表述。

> **Hero 区保持现有文案不变。** 以下为 Hero 之外的各区块修改建议。

#### 2.1 能力统计区（[HomeCapabilityStats.vue](app/components/home/HomeCapabilityStats.vue):9-13）

**现状：** 4个卡片重复出现了产品线、城市数量和流程概述。

**修改建议：** 调整为**差异化数据 + 用户利益**的语言：

| 卡片 | 现状（中文） | 建议改为 |
|------|-------------|---------|
| 批量/PCBA批量出货 | 产能按项目计划确认 | **项目导向排产，交期可控。** |
| 4/产品线结构 | 键鼠外设、运动相机遥控、充电宝模块、定制板卡 | **4 条产品线覆盖主流无线控制与电子板卡需求。** |
| 3城/研发与量产协同 | 杭州、深圳、上海联动 | **杭沪深三地工程资源协同。** |
| 全流程/制造交付支持 | 打样、试产、量产、质检出货 | **从第一天打样到最后一批出货，都在同一体系内完成。** |

| Card | Current (English) | Suggested |
|------|-------------------|-----------|
| Batch/PCBA batch shipment | Capacity confirmed by project plan | **Project-driven scheduling with predictable delivery.** |
| 4/Product line structure | Keyboard/mouse, action camera remote, power bank module and custom PCBA | **Four product directions covering mainstream wireless control and board-level needs.** |
| 3/R&D / production cities | Hangzhou, Shenzhen and Shanghai | **Engineering resources across Hangzhou, Shenzhen and Shanghai.** |
| Full Flow/Manufacturing support | Sample, pilot run, production and QC shipment | **From first prototype to final shipment — all within one accountable system.** |

#### 2.2 关于壹原理区（[HomeAbout.vue](app/components/home/HomeAbout.vue):27-28）

**现状：**
- 中文：`从 PCBA 打样到成品批量出货的制造商。`
- English：`A manufacturer from PCBA sampling to finished product batch shipment.`

**问题**：与制造页 Hero 描述雷同。

**修改建议：**

```
中文（改为）：
"我们不设计产品，我们让产品被可靠地制造出来。"

English（改为）：
"We don't design products — we make them manufacturable and deliverable at scale."

说明：首页About区应聚焦"我们做什么、不做什么"的差异化定位。
```

下方文字（line 28）改为：

```
中文：
"围绕客户的 BOM 清单、工艺规格和交付目标，壹原理将工程验证、供应链接入、批量制造和出货检验组织为一条清晰的交付链。从 PCBA 打样到成品出货，中间每个节点都有记录、有人负责。"

English：
"Around your BOM, process specs and delivery targets, YiYuanLi organizes engineering validation, supply chain integration, batch manufacturing and shipment inspection into a single accountable chain. Every step, from PCBA prototype to finished goods shipment, is documented and owned."
```

#### 2.3 产品展示区（[HomeProductTiles.vue](app/components/home/HomeProductTiles.vue):25-29）

**现状：** lead 段落与产品详情页的标题句高度重叠。

**修改建议：**

```
中文（改为）：
"从一条键盘控制板到一批相机遥控器，每条产品线都按项目独立评估、独立排产、独立交付。"

English（改为）：
"Whether it's one keyboard controller prototype or a batch of camera remotes — every product line is independently assessed, scheduled and delivered per project."

说明：首页产品的 lead 文字强调"项目制"的特色，与详情页区分。
```

#### 2.4 研产协同布局区（[HomeFootprint.vue](app/components/home/HomeFootprint.vue):19-22）

**现状：** 标题和文字与 AboutPage 中的 layout 区域几乎一致。

**修改建议：**

```
中文（改为）：
- 标题："三座城市，各自对准一个制造环节。"
- P1："杭州的运营团队理解交付节奏，深圳的工厂控制贴片与组装质量，上海的工程师在射频和固件层面验证设计。三地各自独立又无缝衔接。"
- P2："这种布局让每个项目天然拥有三个维度的专业判断——供应链可行性、制造可重复性和工程正确性。"

English（改为）：
- Title: "Three cities, each anchored to one manufacturing discipline."
- P1: "Hangzhou's operations team owns delivery rhythm. Shenzhen's factory controls SMT and assembly quality. Shanghai's engineers validate designs at the RF and firmware level. Three cities, working as one chain."
- P2: "This layout gives every project three layers of professional judgment by default — supply chain feasibility, manufacturing repeatability and engineering correctness."
```

#### 2.5 制造支持区（[HomeSupport.vue](app/components/home/HomeSupport.vue):24-25）

**现状：** 4 步流程与制造页面几乎一模一样。

**修改建议：** 首页改为**客户视角**陈述，而非制造术语：

```
中文（改为）：
- 标题："你的项目进入壹原理后，会经历什么？"
- 副标题："每个阶段都有一个明确的对齐节点，你不会被扔进一个黑盒子里。"

English（改为）：
- Title: "What happens after your project reaches YiYuanLi?"
- Subtitle: "Every stage has a clear alignment checkpoint. Your project never disappears into a black box."

4 个步骤的语言也做客户视角调整：
1. "工程打样" → "确认可行性" / "Feasibility Check" 
   "你提供规格，我们出样品和验证数据。"
   "You provide specs; we deliver samples with validation data."
   
2. "试产验证" → "固化一致性" / "Consistency Lock"
   "小批量跑一遍，确认批量也能做出一样的品质。"
   "A small batch to confirm the process can repeat at scale."
   
3. "批量制造" → "进入量产节奏" / "Production Rhythm"
   "供应链就位，产线排入计划，按节奏出货。"
   "Supply chain engaged, line scheduled, shipping to cadence."
   
4. "质检出货" → "放行与交付" / "Release & Deliver"
   "每批附检测记录，你看得到数据再收货。"
   "Every batch ships with inspection records. You see the data before you accept."
```

---

### 【关于我们 About】— 定位：建立信任，展示"深度"

"关于我们"页面应深入阐述公司理念、团队背景和业务逻辑，避免与首页重复的身份声明。

#### 3.1 公司简介区（[AboutPage.vue](app/components/AboutPage.vue):40-48）

**现状：** 两段话与 site.ts 中的 about/company 文本几乎重叠。

**修改建议：** 保留 site.ts 版本作为子页面内容，修改 AboutPage.vue 中的文案，增加**故事性和差异化**：

```
中文（改为）：
P1（保持骨干，调整细节）：
"壹原理科技成立于杭州，深圳和上海分别承担量产供应链与客户工程验证的角色。三地团队加起来，每天处理的都是同一件事——怎么把一块电路板从图纸变成可以批量出货的良品。"

P2（全新撰写）：
"选择我们的客户，通常不是因为没有供应商可选，而是因为需要一家能同时理解 PCB 工艺、射频性能、物料周期和交付节奏的制造伙伴。我们不接所有单——每个项目在进产线之前，都要先通过工程评估和可制造性确认。"

English（改为）：
P1:
"YiYuanLi was founded in Hangzhou, with Shenzhen managing production and supply chain, Shanghai leading customer engineering and validation. Across three cities, the team focuses on one core task — turning a circuit board design into shippable, quality-assured products."

P2:
"Clients choose us not for lack of alternatives, but for a manufacturing partner who understands PCB processes, RF performance, component lead times and delivery cadence — all at once. We don't take every order. Every project passes through engineering assessment and manufacturability review before reaching the production line."
```

#### 3.2 业务范围区（[AboutPage.vue](app/components/AboutPage.vue):180-181）

**现状：**
- 标题：`四类产品方向，按可交付能力组织。`
- 副标题与 site.ts 中文字重叠。

**修改建议：**

```
中文（改为）：
- 标题："每条产品线，都有对应的工程团队和工艺积累。"
- 副标题："我们不做'什么都能做'的承诺，每个方向都基于实际交付过的项目经验。"

English（改为）：
- Title: "Every product direction has a dedicated engineering team and proven process history."
- Subtitle: "We don't promise 'we can do everything.' Each direction is grounded in projects we've actually delivered."
```

#### 3.3 企业文化区（[AboutPage.vue](app/components/AboutPage.vue):216-217）

**现状：** 文化卡片文字与 site.ts 中完全一致。

**修改建议：** 文化理念保持核心不变，但表达方式可以更生动：

将 4 条原则改写为更有画面感的表述（价值观本身不变）：

| 原则 | 现状 | 建议改为（中文） | 建议改为（English） |
|------|------|-----------------|-------------------|
| 工匠精神 | 每个参数有标准、有记录，不接受"差不多"。 | **"一块板子过 AOI，偏差超过阈值就退回，没有例外。"** | **"A board fails AOI by a margin — it goes back. No exceptions."** |
| 务实沟通 | 给方案、给排期、给结果，让项目进度可预期。 | **"回复邮件不用术语堆砌，排期表上的日期就是承诺。"** | **"No jargon in emails. Every date on the schedule is a commitment."** |
| 责任到人 | 明确工程负责人，问题在发生处及时闭环。 | **"每个项目只有一个工程对接口。出了问题不用找'上面'，找他。"** | **"One engineering owner per project. When issues arise, there's no 'escalation maze' — just one accountable person."** |
| 持续改进 | 用每一次交付复盘，改进下一次制造。 | **"每批出货后的复盘笔记，是下一批工艺文件的一部分。"** | **"Post-shipment review notes become part of the next batch's process documentation."** |

---

### 【产品中心 Products】— 定位：展示专业度，体现"定制能力"

产品中心应聚焦**具体规格、技术参数和交付形态**，避免简单重复业务范围页的卡片。

#### 4.1 产品方向区标题（[ProductCenterPage.vue](app/components/ProductCenterPage.vue):36）

**现状：**
- 中文：`不销售标准化成品，按项目确认工程路径与交付形态。`
- English：`No off-the-shelf products. Delivery is confirmed for each project.`

**修改建议：**

```
中文（改为）：
"同一条产品线，不同客户的 BOM 和工艺要求完全不同。所以我们是按项目，不是按 SKU 组织制造。"

English（改为）：
"The same product line can mean entirely different BOMs and process requirements across clients. We organize by project, not by SKU."
```

#### 4.2 应用场景区（[ProductCenterPage.vue](app/components/ProductCenterPage.vue):38）

**现状：**
- 中文：`从实际应用出发，反推产品与制造路径。`
- English：`Start from the real use case, then define the product and manufacturing path.`

**修改建议：**

```
中文（改为）：
"以下场景来自我们实际交付过的项目。如果你做的事跟这些不一样，也欢迎聊聊——我们评估的是制造可行性，不是行业赛道。"

English（改为）：
"These scenarios come from projects we've actually delivered. If yours is different, let's talk anyway — we evaluate manufacturing feasibility, not industry categories."
```

#### 4.3 产品咨询区（[ProductCenterPage.vue](app/components/ProductCenterPage.vue):40）

**现状：**
- 中文：`说明产品方向、应用场景与预计数量。`
- English：`Share the product direction and expected quantity.`

**修改建议：**

```
中文（改为）：
"不需要你有完整的设计文件。告诉我们产品做什么用、大概什么量级、希望什么时候交付——剩下的工程评估交给我们。"

English（改为）：
"You don't need complete design files. Tell us what the product does, the rough volume, and your target timeline — we'll handle the engineering assessment from there."
```

---

### 【制造与服务 Manufacturing】— 定位：传递可靠性，展示"过程可控"

制造页应强调**流程的严谨性和可追溯性**，避免与首页 Support 区使用完全相同的四阶段命名。

#### 5.1 生产服务区（[ManufacturingPage.vue](app/components/ManufacturingPage.vue):40）

**现状：**
- 标题：`四个阶段，一套可追溯的交付标准。`
- 4 个步骤与首页 Support 步骤一致。

**修改建议：** 标题和步骤描述做差异化：

```
中文（改为）：
- 标题："不是流水线，是四个环环相扣的交付关口。"
- 副标题："每个关口都有输出物——样品、数据、签核文件——不交付空气。"

步骤描述改为更工艺化的语言：
1. "工程打样" → "工程验证阶段"
   "输出：工程样品 + 功能验证报告 + BOM 确认清单"
2. "试产验证" → "工艺固化阶段"
   "输出：SMT 参数表 + 测试治具验收单 + 工艺文件签核版"
3. "批量制造" → "量产执行阶段"
   "输出：生产日报 + 过程良率数据 + 异常处理记录"
4. "质检出货" → "放行交付阶段"
   "输出：批次检测报告 + 包装核验单 + 出货通知"

English（改为）：
- Title: "Not assembly lines — four interconnected delivery gates."
- Subtitle: "Every gate produces tangible outputs — samples, data, sign-off documents — never empty promises."

1. "Engineering Sample" → "Engineering Validation Phase"
   "Output: Engineering samples + functional validation report + BOM confirmation checklist"
2. "Pilot Validation" → "Process Lock Phase"
   "Output: SMT parameter sheet + fixture acceptance record + signed process document"
3. "Batch Manufacturing" → "Production Execution Phase"
   "Output: Daily production report + real-time yield data + exception handling log"
4. "QC Shipment" → "Release & Delivery Phase"
   "Output: Batch inspection report + packaging checklist + shipment notice"
```

#### 5.2 工艺流程区（[ManufacturingPage.vue](app/components/ManufacturingPage.vue):41）

**现状：**
- 标题：`每一个制程节点，都能确认并持续跟进。`
- 4 个节点与"生产服务"和"合作路径"高度重叠。

**修改建议：** 工艺流程聚焦**技术动作**而非管理节点：

```
中文（改为）：
- 标题："从 BOM 表到成品箱，每一个动作都有记录。"
- 副标题（新增）："以下四个技术节点定义了壹原理的标准制程路径。每个节点的输入、输出和验收标准在项目启动前就已明确。"

4 个节点改为更技术化的描述：
1. "规格对齐" → 
   "收到设计文件和 BOM 后，工程团队逐一核对：器件是否可采购、封装是否匹配产线工艺、测试点是否覆盖关键功能。任何偏差在此时闭环。"
2. "工程就绪" →
   "物料到位、钢网开孔确认、贴片程序编写、测试治具调试完成。工程团队出具首件检查清单。"
3. "试产验证" →
   "小批量运行完整工艺路径，记录每个工站的参数和良率。与客户共同确认试产结果后再锁定量产工艺文件。"
4. "量产执行" →
   "按固化工艺排产，AOI 和 ICT 在线监控，每批次建独立的质检档案。异常实时通报，不堆积。"

English（改为）：
- Title: "From BOM to shipping carton — every action is recorded."
- Subtitle (new): "Four technical nodes define YiYuanLi's standard process path. Inputs, outputs and acceptance criteria for each node are defined before any project starts."

1. "Spec Alignment" →
   "After receiving design files and BOM, the engineering team verifies: part availability, package-to-line compatibility, and test point coverage for critical functions. Any gaps close here."
2. "Engineering Readiness" →
   "Materials on hand, stencil apertures confirmed, pick-and-place programs written, test fixtures debugged. Engineering issues the first-article checklist."
3. "Pilot Verification" →
   "Run the full process path in low volume. Record parameters and yield at every station. Confirm pilot results with client before locking the production process document."
4. "Production Execution" →
   "Schedule per locked process. AOI and ICT monitor in-line. Every batch gets its own quality archive. Anomalies are flagged in real time — never accumulated."
```

#### 5.3 测试与交付区（[ManufacturingPage.vue](app/components/ManufacturingPage.vue):42）

**现状：** 4 项测试描述与 site.ts 中内容完全相同。

**修改建议：**

```
中文（改为）：
- 标题："我们测的不只是板子好不好，而是每一批和上一批是不是一样好。"
- 副标题（新增）："批次一致性比单板完美更重要。以下测试项目围绕这个目标设计。"

4 项测试调整为强调"为什么测"而非"测什么"：
1. "功能测试" →
   "不是抽测，是每板必过的自动化测试站。覆盖上电、连接、按键响应、功耗电流等基础功能。"
2. "射频校准" →
   "2.4G/BLE 频段的频偏和功率如果不校准，同一批次里可能有一半的信号强度不同。我们每板校准，每批出具分布图。"
3. "环境可靠性" →
   "按产品实际使用场景选择测试项——不是所有板子都需要防水，但如果是户外产品，一定会做。"
4. "出货检验" →
   "最后一道关卡：外观、数量、标签、包装、附件清单、出货报告——六个维度一致才能放行。"

English（改为）：
- Title: "We're not just checking if a board is good — we're checking if this batch matches the last one."
- Subtitle (new): "Batch-to-batch consistency matters more than single-unit perfection. Every test below serves that goal."

1. "Functional Test" →
   "Not a spot check — every board passes through an automated test station covering power-up, connectivity, key response and current draw."
2. "RF Calibration" →
   "Without per-board calibration on 2.4G/BLE frequency offset and power, half the batch can show different signal strength. We calibrate every board and ship the distribution chart with the batch."
3. "Environmental Reliability" →
   "Tests are selected by actual use case — not every board needs waterproofing, but if it's an outdoor product, it absolutely gets tested."
4. "Shipment Inspection" →
   "The final gate: appearance, quantity, labels, packaging, accessory checklist, shipment report — six dimensions must align before release."
```

---

### 【联系我们 Contact】— 定位：降低接触门槛，传递"可接近感"

联系页应让客户感到**沟通路径清晰**，避免与首页 CTA 语言重复。

#### 6.1 联系方式区（[ContactPage.vue](app/components/ContactPage.vue):99-106）

**现状：** 标题和文字与 site.ts 中 contact/info 高度相似。

**修改建议：**

```
中文（改为）：
- 标题："三座城市，一个统一的项目接口。"
- 副标题："你不用判断该找杭州、深圳还是上海——通过下方表单提交需求，我们会根据项目类型安排最合适的对接人。"

English（改为）：
- Title: "Three cities, one project interface."
- Subtitle: "You don't need to figure out whether to contact Hangzhou, Shenzhen or Shanghai. Submit your project via the form below and we'll route it to the right team."

4 个城市卡片的描述也做微调：
1. 杭州总部 → "承接所有客户需求的入口，负责项目统筹与进度管理。"
2. 深圳量产中心 → "SMT 产线、物料仓库和出货质检都在这。需要看厂？从这里开始。"
3. 上海研发中心 → "固件工程师和射频实验室在这里。技术细节最好是当面聊。"
4. 工作时间 → "工作日 09:00-18:00。邮件和表单 24 小时开放。"

English（改为）：
1. Hangzhou Headquarters → "The entry point for all client inquiries — project coordination and progress management."
2. Shenzhen Production Center → "SMT lines, component warehouse and QC are here. Want a factory tour? Start here."
3. Shanghai R&D Center → "Firmware engineers and RF lab are here. Technical details are best discussed in person."
4. Business Hours → "Weekdays 09:00-18:00. Email and forms are open 24/7."
```

#### 6.2 业务咨询区（[ContactPage.vue](app/components/ContactPage.vue):122-130）

**现状：** 咨询引导语与产品咨询页面类似。

**修改建议：**

```
中文（改为）：
- 标题："不用准备完美的需求文档，把你知道的告诉我们就好。"
- 副标题："产品类型、预计数量区间、希望交付的时间、有没有样品或图纸——有哪项填哪项。缺的部分我们会在沟通中一起补齐。"

English（改为）：
- Title: "You don't need a perfect requirements document — just share what you know."
- Subtitle: "Product type, estimated volume range, target timeline, whether you have samples or drawings — fill in whatever you have. We'll fill in the gaps together during follow-up."
```

---

### 【site.ts 数据层】— 独立于组件层的第二套文案

[site.ts](app/data/site.ts) 中的 `pages` 对象（line 99-349）为子页面（`[slug].vue`）提供数据，与页面级组件（AboutPage/ProductCenterPage/ManufacturingPage/ContactPage）形成了**两套并行文案**。

**当前关系：**
- `/about/company` → 使用 site.ts 的 about.company
- `/about` → 使用 AboutPage.vue（硬编码）
- 两者内容相近但措辞略有不同

#### 修改策略：

**方案 A（推荐）**：让 site.ts 作为子页面数据源（保持现有结构），将其文案调整为"详情版"——比页面组件更长、更具体。页面组件文案改为"概要版"——更短、更有冲击力。

**方案 B**：将 site.ts 的文案也按以上各节建议同步修改，保持两套文案一致但有层级区别（site.ts = 详细版，组件 = 精炼版）。

无论采用哪种方案，site.ts 中需要改动的具体位置如下：

| site.ts 位置 | 当前文案特征 | 建议方向 |
|-------------|------------|---------|
| about.company.description (line 104) | 与首页Hero同句 | 改为公司成立背景/初衷 |
| about.business.description (line 121) | "四条产品线，按项目定制" | 改为"每个项目独立评估工艺与交期" |
| about.culture.description (line 140) | "四个基本原则" | 改为"我们怎么做事，不靠口号" |
| products.detail.description (line 161) | "四类产品方向，按项目定制" | 与 business 区分 |
| manufacturing.production.description (line 260) | 与首页Support一致 | 改为聚焦交付节奏 |
| manufacturing.process.description (line 279) | 与生产服务重叠 | 改为聚焦技术节点 |
| manufacturing.testing.description (line 298) | "批次一致性建立质量闭环" | 保留，这是好文案 |
| contact.info.description (line 319) | "三城布局…" | 改为"一个入口，路由到三城" |

---

## 三、C TA（行动号召）文案统一优化

当前全站 CTA 按钮用语缺乏层次感，建议按页面意图做差异：

| 位置 | 现状 | 建议 |
|------|------|------|
| 首页 Support CTA | "联系我们" | **"提交项目信息"** |
| 关于我们底部 | "业务咨询" | **"开启合作对话"** |
| 产品咨询按钮 | "提交咨询" | **"发送产品需求"** |
| 联系页按钮 | "提交咨询" | **"开始沟通"** |

English:

| Location | Current | Suggested |
|----------|---------|-----------|
| Home Support CTA | "Contact Us" | **"Submit Project Info"** |
| About Bottom | "Business Inquiry" | **"Start a Conversation"** |
| Product Inquiry | "Submit Inquiry" | **"Send Product Requirements"** |
| Contact Form | "Submit Inquiry" | **"Start the Conversation"** |

---

## 四、导航描述文案统一优化

[site.ts](app/data/site.ts):34-74 中的导航项 `description` 字段用于子导航展示，目前与内容标题高度重复：

| 导航项 | 现状 | 建议 |
|--------|------|------|
| 公司简介 | "企业概况、制造能力" | "我们是谁，怎么做事" |
| 业务范围 | "产品线与制造能力" | "四类产品方向与定制流程" |
| 企业文化 | "工匠精神、务实高效、协同担当、持续精进" | "产线上的原则，不只是墙上的口号" |
| 产品详情 | "产品线、规格与交付形态" | "技术规格、核心能力与交付范围" |
| 应用场景 | "行业应用与解决方案" | "按场景匹配产品与方案" |
| 产品咨询 | "样品、试产与定制需求" | "提交需求，获取工程评估" |
| 生产服务 | "打样、试产、量产、出货" | "从样品到出货的完整路径" |
| 工艺流程 | "PCBA 制程节点" | "规格→设计→试产→量产" |
| 测试与交付 | "测试标准与质检流程" | "确保每一批和上一批一样好" |
| 联系方式 | "办公城市与业务入口" | "三城布局与对接方式" |
| 业务咨询 | "商务合作与来访预约" | "提交合作需求或预约来访" |

English equivalents updated accordingly.

---

## 五、Footer 文案微调

[SiteFooter.vue](app/components/SiteFooter.vue) 中的 link group 标题目前直接复用导航 label，建议 footer 使用更简洁的版本以区别于主导航。此项为可选优化。

---

## 六、修改优先级建议

按**用户感知度**和**SEO 影响**排序：

| 优先级 | 修改项 | 影响范围 |
|--------|--------|---------|
| 🔴 P0 | 产品四方向去重（R2） | 出现在 5+ 处，严重重复 |
| 🔴 P0 | 打样-出货流程去重（R3） | 出现在 4+ 处 |
| 🟡 P1 | 三城布局去重（R4） | 出现在 4 处 |
| 🟡 P1 | 制造页三区标题差异化（R5） | 子页面内部 |
| 🟢 P2 | CTA 按钮差异化 | 细节优化 |
| 🟢 P2 | 导航描述优化 | 辅助导航体验 |
| ⚪ P3 | site.ts 数据层文案微调 | 子页面 SEO |
| ⚪ P3 | Footer 文案微调 | 可选 |

---

## 七、文件改动清单

修改将涉及以下文件（按改动量排序）：

| 文件 | 改动量 | 说明 |
|------|--------|------|
| [HomeAbout.vue](app/components/home/HomeAbout.vue) | 标题+正文 | About 区文案 |
| [HomeProductTiles.vue](app/components/home/HomeProductTiles.vue) | lead 段落 | 产品区引导语 |
| [HomeFootprint.vue](app/components/home/HomeFootprint.vue) | 标题+2 段话 | 布局区文案 |
| [HomeSupport.vue](app/components/home/HomeSupport.vue) | 标题+4 步骤 | Support 区文案 |
| [HomeCapabilityStats.vue](app/components/home/HomeCapabilityStats.vue) | 4 个卡片 | 统计数据描述 |
| [AboutPage.vue](app/components/about/AboutPage.vue) | 全部 3 区 | 关于页全页 |
| [ProductCenterPage.vue](app/components/ProductCenterPage.vue) | 3 个 section | 产品页全页 |
| [ManufacturingPage.vue](app/components/ManufacturingPage.vue) | 全部 3 区 | 制造页全页 |
| [ContactPage.vue](app/components/ContactPage.vue) | 2 个 section | 联系页全页 |
| [site.ts](app/data/site.ts) | pages 对象 + nav 描述 | 数据层文案 |

---

> **下一步**：请审阅以上方案，确认后我可以逐文件执行修改。你可以选择：  
> ① 全部采纳，一次性修改所有文件  
> ② 按优先级分批修改（先 P0，再 P1…）  
> ③ 对特定页面的方案做二次调整后再执行
