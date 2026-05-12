# 所有技能汇总

---

## 1. codegen-diagram - 代码生成·项目图表

```yaml
---
name: codegen-diagram
description: 基于当前项目/代码生成 Draw.io 图表，支持技术栈图、系统架构图、数据结构图、E-R 图四种类型。输出符合 Draw.io 语法的 .drawio 文件（mxGraph XML），可直接导入 Draw.io 编辑。当用户提到技术栈、系统架构、数据结构、E-R 图时使用。
---
```

### 任务识别

| 用户表述 / 关键词 | 执行 |
| ------------------ | ----------------------------- |
| 技术栈、整体技术栈、组件选型 | `reference/tech-stack.md` |
| 系统架构、分层结构、调用流程 | `reference/system-arch.md` |
| 数据结构图、表结构图、实体字段关系图 | `reference/data-structure.md` |
| E-R 图、实体关系图、数据库关系图 | `reference/er-diagram.md` |

### 使用时机

- 用户需要根据当前项目画技术栈图、系统架构图、数据结构图或 E-R 图
- 用户提到「根据当前项目」「根据代码」「画我们系统的……」

### 通用规范（四种图表共用）

#### Draw.io 基础
- 使用 **mxGraphModel**，画布背景 `#FFFFFF`
- 仅使用 Draw.io 内置形状，确保可立即打开与编辑
- 节点标签简洁，符合技术文档表达习惯

#### 色彩与字体

| 用途 | 颜色值 |
| ------ | ------- |
| 主色调 | `#3366CC` |
| 副色调 | `#7FBFFF` |
| 强调色 | `#FF9966` |
| 深色背景字体 | `#FFFFFF` |
| 浅色背景字体 | `#333333` |
| 画布背景 | `#FFFFFF` |

- 字体：Helvetica，字号 11–13
- 连接线：`endArrow=classicBlockThin` 或 `blockThin`

#### 输出要求
1. 图表总览（1-2 段文字）
2. 完整 mxGraph XML（可保存为 .drawio）
3. 导入与使用说明
4. 图题与论文引用建议

---

## 2. codegen-doc - 代码生成·项目文档

```yaml
---
name: codegen-doc
description: 基于当前项目/代码生成各类文档，支持论文章节、项目梳理、重点问题、简历项目描述四种类型。当用户提到生成论文章节、项目梳理、技术难点、简历项目描述时使用。
---
```

### 任务识别

| 用户表述 / 关键词 | 执行 |
| ------------------ | ------ |
| 论文章节、系统设计、总体设计、详细设计 | `reference/thesis-chapter.md` |
| 项目梳理、项目文档结构、按格式梳理 | `reference/overview.md` |
| 重点问题、技术难点、待解决问题、项目风险 | `reference/key-issues.md` |
| 简历项目描述、项目经历、按简历格式 | `reference/resume-format.md` |

### 使用时机

- 用户需要根据当前项目生成论文章节、项目梳理、重点问题清单或简历项目描述
- 用户提到「根据当前项目」「根据代码」「按这个格式……」

### 通用原则

- **不编造**：未在仓库中出现的内容不写入
- **有据可依**：尽量从代码、注释、README、文档中抽取
- **格式遵从**：用户提供格式/模板时，严格按格式组织输出

---

## 3. dev-workflow - 开发流程五步法

```yaml
---
name: dev-workflow
description: 开发流程五步法。支持需求理解、方案设计、代码实现、代码审查、Bug 修复。当用户提到「需求分析」「方案设计」「代码实现」「代码审查」「理解需求」「技术设计」「开始写代码」「Review」「检查代码」「bug」「报错」「崩溃」「异常」「出错了」时使用。
---
```

### 使用时机

- 用户描述新功能/项目想法，需要需求分析
- 用户提到「方案设计」「架构设计」「怎么实现」
- 用户提到「代码实现」「开始写代码」「帮我实现」
- 用户提到「代码审查」「Review」「检查代码」「看看有没有问题」
- 用户提到「bug」「报错」「崩溃」「异常」「不工作」「出错了」「测试失败」

### Step 1：识别当前步骤

| 步骤 | 文件 | 触发关键词 |
| ------ | ------------------------------------------------ | ------------------------- |
| 需求理解 | [requirement.md](reference/requirement.md) | 需求分析、理解需求、整理需求、帮我梳理 |
| 方案设计 | [design.md](reference/design.md) | 方案设计、技术设计、架构设计、怎么实现 |
| 代码实现 | [implementation.md](reference/implementation.md) | 代码实现、开始写代码、帮我实现、写一下 |
| 代码审查 | [review.md](reference/review.md) | 代码审查、Review、检查代码、看看有没有问题 |
| Bug 修复 | [bug-fix.md](reference/bug-fix.md) | bug、报错、崩溃、异常、不工作、出错了、测试失败 |

### Step 2：收集输入

- **需求理解**：从用户描述或对话中提取功能想法、约束条件
- **方案设计**：确认已有需求文档，或简要收集关键信息
- **代码实现**：确认已有技术方案，或根据需求快速拟定实现思路
- **代码审查**：明确审查范围（哪些文件/模块）
- **Bug 修复**：确认错误信息、复现步骤、环境信息

### Step 3：执行、输出与自动落盘

读取对应 reference 中的完整流程，按步骤执行，输出符合该阶段要求的交付物。

其中以下步骤必须自动写入文档：

- **需求理解**：
  - 单模块/未指定模块：将最终需求文档**追加写入**当前工作目录的 `docs/需求理解.md`
  - 多模块且已识别模块名：将最终需求文档**追加写入** `docs/<module>/需求理解.md`
- **方案设计**：
  - 单模块/未指定模块：将最终方案文档**追加写入**当前工作目录的 `docs/方案设计.md`
  - 多模块且已识别模块名：将最终方案文档**追加写入** `docs/<module>/方案设计.md`
- **代码审查**：
  - 单模块/未指定模块：将最终审查报告**追加写入**当前工作目录的 `docs/代码审查.md`
  - 多模块且已识别模块名：将最终审查报告**追加写入** `docs/<module>/代码审查.md`

### 注意事项

- 流程串联：需求理解 → 方案设计 → 代码实现 → 代码审查 → Bug 修复；每步完成后提示用户进入下一阶段
- 上游缺失时：提示用户先完成前置步骤，或简要收集关键信息后继续
- 需求理解、方案设计与代码审查阶段默认必须自动落盘（追加写入），不要覆盖历史记录

---

## 4. drawio-diagram - Draw.io 图表

```yaml
---
name: drawio-diagram
description: 生成标准 Draw.io (.drawio) 格式的可视化图表；支持从零生成与风格迁移两种模式。从零生成：AI/深度学习模型架构图、算法流程图、系统架构图；教育/考试示意图（数学几何、物理受力/电路/光路、化学实验/分子结构、生物细胞/遗传/食物链、地理经纬/圈层/地形、历史时间轴/朝代/制度、语文结构图）。风格迁移：参考图 + 内容 → 按参考图风格生成新图。确保 XML 格式正确，可直接在 Draw.io 中打开编辑。
---
```

### Step 0：任务识别

| 条件 | 执行 |
| ------ | ------ |
| 用户提供**参考图**，且希望「按这张图的风格」画新图 | 执行 `reference/style-migration.md` |
| 数学几何图形（三角形、圆、圆柱、坐标系、数轴、韦恩图等） | 执行 `reference/edu-math.md` |
| 物理示意图（受力图、电路图、光路图、运动轨迹等） | 执行 `reference/edu-physics.md` |
| 化学示意图（实验装置、原子结构、分子结构、方程式注解等） | 执行 `reference/edu-chemistry.md` |
| 生物示意图（细胞结构、遗传图解、食物链/食物网等） | 执行 `reference/edu-biology.md` |
| 地理示意图（经纬网、地球圈层、地形剖面、大气环流等） | 执行 `reference/edu-geography.md` |
| 历史示意图（时间轴、朝代更迭、政治制度、因果关系等） | 执行 `reference/edu-history.md` |
| 语文示意图（文章结构、古诗词脉络、句子成分、议论文结构等） | 执行 `reference/edu-chinese.md` |
| 其他（AI/深度学习模型架构、算法流程、系统架构等） | 执行 `reference/tech-diagram.md` |

### 使用时机

#### 从零生成
- 用户需要为深度学习模型（如 Transformer、CNN、RNN 等）生成架构图
- 用户需要绘制算法流程图、数据流图、系统架构图
- 用户需要可视化特定概念（如感受野、注意力机制、特征提取过程等）
- **用户需要教育/考试示意图**：
  - 数学：几何图形（三角形、圆、圆柱、圆锥、棱柱等）、数轴、韦恩图、坐标系
  - 物理：受力分析图、电路图、光路图、运动轨迹图
  - 化学：实验装置图、原子/分子结构、化学反应方程式注解
  - 生物：细胞结构图、遗传图解、食物链/食物网
  - 地理：经纬网、地球圈层、地形剖面图、大气环流/风带
  - 历史：时间轴、朝代更迭图、政治制度示意、因果关系图
  - 语文：文章结构图、古诗词脉络图、句子成分分析、议论文结构图
- 用户提到「画个图」「生成架构图」「可视化模型结构」「绘制流程图」「画示意图」「考试题图」等需求

#### 风格迁移
- 用户提供参考图，希望「按这个风格画」「照着这个排版/配色画」

### 通用规范（两种模式共用）

#### 1. XML 格式严格性
- ✅ 所有标签必须正确闭合：`<mxCell>` 对应 `</mxCell>`，绝不能写成 `</mCell>`
- ✅ 使用 `vertex="1"` 标记节点，`edge="1"` 标记连线
- ✅ 每个元素必须有唯一 `id`，从 0 开始递增
- ✅ 特殊字符必须转义：`&` → `&amp;`，`<` → `&lt;`，`>` → `&gt;`

#### 2. 标准文件结构
```xml
<mxfile host="app.diagrams.net">
  <diagram name="图表名称" id="图表id">
    <mxGraphModel dx="1200" dy="800" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="1" pageScale="1" pageWidth="宽度" pageHeight="高度" background="#F5F5DC">
      <root>
        <mxCell id="0"/>
        <mxCell id="1" parent="0"/>
        <!-- 所有图形元素从 id="2" 开始 -->
      </root>
    </mxGraphModel>
  </diagram>
</mxfile>
```

#### 3. 常用样式
- **节点**：`rounded=1;whiteSpace=wrap;html=1;fillColor=#颜色;strokeColor=#333333;strokeWidth=1;fontSize=11`
- **连线**：`edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;strokeColor=#000000;strokeWidth=2;endArrow=classic`
- **虚线（残差）**：`dashed=1`

#### 4. 输出要求
1. 图表说明（2-3 句）
2. 使用指南：Draw.io 打开、导出 PNG/SVG/PDF、图题与论文引用示例

---

## 5. excalidraw-diagram - Excalidraw 手绘图

```yaml
---
name: excalidraw-diagram
description: 基于文字说明或结构信息，生成可直接在 Excalidraw 中打开的手绘风 .excalidraw 图表；支持系统架构图、流程图、数据结构图与自由白板草图，输出标准 Excalidraw JSON。
---
```

### 使用时机

- 用户希望生成「手绘风」的系统架构图、模块依赖图、业务流程图、数据流图等
- 用户提到「画个架构图」「画流程图」「画模块关系图」「用 Excalidraw 画图」等需求
- 用户已有较清晰的模块/步骤/实体列表，希望整理成一张结构化示意图

### 支持图类型

- **系统架构图**：用户 / 前端 / 后端服务 / 数据库 / 外部系统等
- **业务流程图 / 近似时序图**：按照步骤或事件顺序，自上而下或自左向右
- **数据结构 / 模块依赖图**：实体之间的关联、依赖关系
- **自由白板草图**：对论文结构、研究框架、任务分解等进行发散式可视化

### 输入格式（在聊天中的推荐写法）

请引导用户尽量按照如下结构提供信息（中文即可）：

- **图类型**：系统架构图 / 流程图 / 数据结构图 / 自由草图
- **内容来源**：自由描述 / 论文大纲 / 代码结构 / 接口列表 等
- **核心要素**：
  - 节点：列出主要模块 / 实体 / 步骤（可分组）
  - 关系：说明谁连接谁、方向与含义（如「用户 → Web 前端」「服务 A 调用 服务 B」）
- **布局偏好**：自上而下 / 自左向右 / 分层布局（可选）
- **分组逻辑**：按子系统、按层次（前端/后端/存储等，可选）
- **颜色规则**：不同类型节点的颜色偏好（可选，若未指定则使用默认配色）

### 生成规则（Agent 内部步骤）

1. **解析输入，构建抽象模型**
   - 抽取所有节点：为每个模块/实体/步骤分配唯一 id、名称与类型
   - 抽取所有关系：source、target、可选 label（调用方式、数据流向等）
   - 确定层次信息：根据图类型与用户的布局偏好，将节点归入不同层（如「用户层 / 前端层 / 服务层 / 数据层」）

2. **简单布局策略（坐标分配）**
   - 不追求复杂自动排版，只需给出「合理、可读」的初始位置
   - 粗略设定 `x, y` 坐标，例如：同层 y 固定、x 按索引递增；不同层 y 按层级间距递增

3. **Excalidraw 元素生成约定（含默认箭头与配色）**
   - **节点元素（默认样式）**：使用 `rectangle` 或 `round rectangle` 表示模块/实体/步骤
   - **连线元素（默认箭头）**：使用 `arrow` 连接相关节点
   - **整体风格**：依赖 Excalidraw 的手绘渲染风格，不需要手动模拟抖动

4. **Excalidraw 文件结构要求**
   - 顶层应符合 Excalidraw 官方 `.excalidraw` JSON 结构
   - 所有元素 id 必须唯一

### 输出格式

Agent 输出必须严格分为两部分：

- **Part 1 [Diagram Explanation]**：用中文简要说明本图的层次结构、各类节点的含义以及主要连线关系
- **Part 2 [Excalidraw JSON]**：输出一个**完整、可直接保存为 `.excalidraw` 文件**的 JSON

---

## 6. frontend-design - 前端界面设计

```yaml
---
name: frontend-design
description: 创建具有高设计品质、可交付生产的前端界面。当用户要求构建 Web 组件、页面、海报或应用（如官网、落地页、仪表盘、React/Vue 组件、HTML/CSS 布局，或对任意 Web UI 进行样式/美化）时使用本技能。产出有创意、打磨到位且避免「AI 通用审美」的代码与界面设计。
license: Complete terms in LICENSE.txt
---
```

### 设计思维

动手写代码前，先理解上下文并**选定一个明确、大胆的美学方向**：

- **目的**：这个界面解决什么问题？谁在用？
- **调性**：选一个鲜明风格并贯彻到底
- **约束**：技术条件（框架、性能、可访问性等）
- **差异化**：什么会让用户**过目不忘**？

### 前端美学指南

#### 字体与排版
- 选用**有辨识度、耐看、有趣**的字体，避免 Arial、Inter、思源黑体等「默认感」过强的选择
- 标题用一款有表现力的展示字体，正文用一款清晰易读的字体
- 建立清晰的**字号与字重层级**

#### 色彩与主题
- 围绕一套**统一的色彩体系**，用 CSS 变量管理
- **主色明确 + 少量高对比强调色**
- 兼顾**无障碍**：重要文字与背景对比度建议 ≥ 4.5:1

#### 动效与微交互
- 用动画营造反馈与氛围
- **集中做好少数高光时刻**
- 适度使用滚动触发、悬停状态，让交互有惊喜感
- 尊重用户偏好：通过 `prefers-reduced-motion` 媒体查询为「减少动效」用户提供静态或简化动效

#### 空间与版式
- **非常规布局**：不对称、重叠、斜线走向、打破网格的元素
- **留白（负空间）**：要么给足留白、营造呼吸感，要么刻意做高密度信息排布

### 禁忌：避免「AI 通用审美」

**不要**使用以下套路：
- 泛滥的字体：Inter、Roboto、Arial、系统默认字体堆砌
- 陈词滥调的配色：尤其是白底 + 紫色/蓝色渐变
- 机械的、模板化的布局与组件样式

### 实现复杂度与美学一致

重要：实现量要和美学目标匹配。
- **繁复/张扬**的风格：需要更完整的动效、层次和细节代码
- **极简/克制**的风格：需要克制的代码、精确的间距、字体与细微对比，少即是多

### 可访问性（WCAG 导向）

- **可感知**：内容可被不同用户感知
- **可操作**：支持键盘、触控与指针
- **可理解**：结构清晰，语义化 HTML
- **健壮**：兼容主流浏览器与辅助技术

---

## 7. md-report-summary - Markdown 周报/汇报/总结/介绍

```yaml
---
name: md-report-summary
description: 生成高质量 Markdown 周报、工作汇报、总结、介绍等文档。无草稿时从 Web 搜索并总结；有草稿时结合草稿整理、润色、补充。当用户提到周报、工作汇报、总结、介绍、述职、复盘时使用。
---
```

### 一、任务识别

| 文档类型 | 触发词 |
| ---- | --------------------- |
| 周报 | 周报、本周总结、weekly report |
| 工作汇报 | 工作汇报、汇报材料、进度汇报 |
| 总结 | 总结、复盘、阶段总结、项目总结 |
| 介绍 | 介绍、简介、项目介绍、个人介绍 |

### 二、流程分支

| 情况 | 执行 |
| --------- | ----------- |
| **未提供草稿** | 执行「三、无草稿流程」 |
| **已提供草稿** | 执行「四、有草稿流程」 |

### 三、无草稿流程

1. **确认信息**：向用户确认主题、时间范围、受众、重点方向
2. **Web 搜索**：用 `WebSearch` 搜索相关背景、行业进展、最佳实践
3. **选模板**：按 [reference/templates.md](reference/templates.md) 选择对应模板
4. **撰写**：按「六、写作质量标准」填充内容并输出

### 四、有草稿流程

1. **读取草稿**：读取用户粘贴的内容或文件路径中的草稿
2. **分析草稿**：识别结构完整性、遗漏点、可优化表述
3. **整理输出**：
   - 表格、列表、引用块、数据、图片**全部原样保留，不删减、不概括**
   - 图片引用 `![描述](路径)` 路径不可修改，原样保留
   - 润色语句、理顺段落逻辑、补充过渡语
   - 缺失章节可用 `WebSearch` 补充，但需注明为补充内容
4. **输出**：整理后的完整 Markdown

### 五、通用原则

- **不省略**：有草稿时，原内容（表格、数据、图片、引用块）全部保留
- **不编造**：不虚构草稿中不存在的事实
- **图片原样**：`![描述](路径)` 中的路径绝对不能修改
- **格式统一**：标题层级清晰，列表、表格按需使用

### 六、写作质量标准

#### 内容层面
- **有结论，不只有陈述**：每个工作项应写清楚"做了什么 → 结果/进展如何"
- **数据具体**：尽可能保留时间、数量、百分比等量化信息
- **问题定位清晰**：问题描述需包含"现象 → 根因 → 影响范围"三要素
- **计划可执行**：下周计划要具体，写清楚目标和预计时间

#### 结构层面
- 用**小标题**区分不同业务模块
- 多项工作优先用**表格**呈现对比
- 重要结论或推荐可用**引用块（`>`）**突出

---

## 8. paper-write - 本科&硕士学位论文撰写

```yaml
---
name: paper-write
description: 本科与硕士学位论文全流程撰写辅助。支持大纲审核（理工科/文科）、结构仿写（通用/实验/绪论/摘要；文科含文献综述、案例分析、对策建议、文科绪论与摘要）、参考文献获取、融合、润色（含实验章节/文科章节）、缩写、扩写、防 AIGC、中英互译、结构化信息提取。当用户提到论文撰写、大纲审核、论文章节仿写、参考文献、论文润色、防 AIGC、论文翻译、文科论文、文献综述、对策建议时使用。
---
```

### 使用时机

- 用户需要审核/优化论文大纲（理工科 / 文科区分）
- 用户需要仿写论文章节（绪论、摘要、实验章节等；**文科**另含文献综述、案例分析、对策建议及文科版绪论/摘要）
- 用户需要参考文献匹配与 GB/T 7714 格式
- 用户需要润色、缩写、扩写、去 AI 化（实验章节用实验润色，文科章节用文科润色）
- 用户需要中英互译
- 用户需要从论文中提取结构化信息（用于答辩 PPT 等）

### Step 1：识别任务类型

根据用户需求选择对应 reference 文件执行。

#### 大纲审核

| 适用 | 文件 |
| ------ | ------ |
| **理工科**（计算机/电子/机械/土木等） | [outline-review-science.md](reference/outline-review-science.md) |
| **文科**（文学/经管/教育/法学/传媒等） | [outline-review-liberal.md](reference/outline-review-liberal.md) |

#### 结构仿写

**通用**（理工/文科均可）

| 任务 | 文件 |
| ------ | ------ |
| 通用章节（任一章节仿写） | [structure-imitate-general.md](reference/structure-imitate-general.md) |

**理工**

| 任务 | 文件 |
| ------ | ------ |
| 绪论 | [structure-imitate-science-introduction.md](reference/structure-imitate-science-introduction.md) |
| 摘要 | [structure-imitate-science-abstract.md](reference/structure-imitate-science-abstract.md) |
| 实验章节 | [structure-imitate-science-experiment.md](reference/structure-imitate-science-experiment.md) |

**文科**

| 任务 | 文件 |
| ------ | ------ |
| 绪论 | [structure-imitate-liberal-introduction.md](reference/structure-imitate-liberal-introduction.md) |
| 摘要 | [structure-imitate-liberal-abstract.md](reference/structure-imitate-liberal-abstract.md) |
| 文献综述 / 理论章节 | [structure-imitate-liberal-literature-review.md](reference/structure-imitate-liberal-literature-review.md) |
| 案例分析 / 调研实证 | [structure-imitate-liberal-case-analysis.md](reference/structure-imitate-liberal-case-analysis.md) |
| 对策与建议 | [structure-imitate-liberal-policy.md](reference/structure-imitate-liberal-policy.md) |

#### 问题与格式检查

| 任务 | 文件 |
| ------ | ------ |
| 问题与格式检查（错别字 / 标点 / 版式 / 图表与公式编号 / 章节引用等） | [check-issues-and-format.md](reference/check-issues-and-format.md) |

#### 参考文献与融合

| 任务 | 文件 |
| ------ | ------ |
| 参考文献获取（GB/T 7714） | [references.md](reference/references.md) |
| 融合 | [merge.md](reference/merge.md) |

#### 润色

| 适用 | 文件 |
| ------ | ------ |
| **通用** | [polish.md](reference/polish.md) |
| **实验章节**（理工） | [polish-science-experiment.md](reference/polish-science-experiment.md) |
| **文科章节** | [polish-liberal.md](reference/polish-liberal.md) |

#### 缩写、扩写、防 AIGC

| 任务 | 文件 |
| ------ | ------ |
| 缩写 | [abbreviate.md](reference/abbreviate.md) |
| 扩写 | [expand.md](reference/expand.md) |
| 防 AIGC（去 AI 痕） | [anti-aigc.md](reference/anti-aigc.md) |

#### 翻译

| 方向 | 文件 |
| ------ | ------ |
| 中 → 英 | [zh-to-en.md](reference/zh-to-en.md) |
| 英 → 中 | [en-to-zh.md](reference/en-to-zh.md) |

#### 结构化信息提取

| 任务 | 文件 |
| ------ | ------ |
| 提取（用于答辩 PPT 等） | [extract-structured.md](reference/extract-structured.md)（完成后可询问是否串联答辩 PPT 生成） |

### Step 2：收集输入

- **多输入任务**（如绪论仿写需【参考范文】【论文大纲】【个人草稿】）：解析用户消息中的【】标记、追问缺失项、或读取用户指定的工作区文件，收齐后再执行
- **单输入任务**：直接从用户消息或粘贴内容提取

### Step 3：执行并输出

读取对应 reference 中的 Prompt，按其中 Role/Task/Constraints/Output Format 执行，输出符合要求的正文或结构化结果。

### 注意事项

- **Word 适配**：严禁 Markdown，中文与英文/数字/公式之间加空格，全角中文标点
- **去 AI 化**：避免「显著提升」「极大增强」「卓越表现」「不仅如此」等
- **信息零丢失**：严禁删除实验参数、数据、核心论点
- **撰写顺序**：先做后写、由内向外——先完成方法章与实验，再写绪论与摘要

---

## 9. pptgen-drawio - PPT 多页 Draw.io 生成

```yaml
---
name: pptgen-drawio
description: 根据论文或汇报内容生成多页 Draw.io 格式 PPT，支持论文答辩与通用汇报两种模式，自动导出为 .pptx。当用户提到论文答辩 PPT、答辩幻灯片、通用 PPT、汇报 PPT、根据模板生成 PPT、drawio2pptx 时使用。
---
```

### 模式识别

| 模式 | 使用时机 | 内容来源 | 默认页序 | 输出文件 |
| ------ | -------- | -------- | -------- | -------- |
| **论文答辩** | 学位论文答辩、开题、预答辩 | paper-write 结构化提取 | 封面→目录→背景→现状→方法→创新点→实验→结论→致谢→Q&A | `paper-defense.drawio` |
| **通用汇报** | 工作汇报、产品介绍、演讲 | 用户消息提取/生成 | 封面→目录→节标题→内容页→总结→致谢→Q&A | `general-presentation.drawio` |

### Step 0：用户自定义模板（可选，两种模式共用）

若用户提供了自己的 `.pptx` 模板文件：
1. **模板放置**：将 `.pptx` 放入 `ppt_template/` 目录
2. **运行样式提取**：在 skill 根目录下执行：
   ```bash
   python scripts/analyze_pptx.py ppt_template/xxx.pptx reference/style-custom.md
   ```
3. 读取 `reference/style-custom.md` 作为「自定义风格」继续

### Step 1：确定内容与风格（两种模式共用）

#### 1.1 确定内容
- **论文答辩**：若用户只有论文全文，先调用 paper-write 的「结构化信息提取」；若已提供结构化信息，从消息中提取【论文题目】【学科方向】【答辩时长】【论文结构/目录】【各章核心内容】【创新点/贡献】等，缺失则追问
- **通用汇报**：从用户消息中提取幻灯片大纲及内容，或根据核心需求扩展为完整结构

#### 1.2 选择风格

两种模式均可选择以下风格之一：

| # | 风格 | 主色 | 强调色 | reference 文件 |
| --- | ------ | ------ | -------- | --------------- |
| 1 | 经典学术 / 商务严谨 | `#1B2A4A` | `#C9A84C` | `reference/style1-classic-academic.md` |
| 2 | 现代极简 / 大字报感 | `#231F20` | `#F5C638` | `reference/style2-minimal-bigtype.md` |
| 3 | 暖色学术 / 亲和力 | `#2C5160` | `#B7472A` | `reference/style3-warm-academic.md` |
| 4 | 科技明快 / 现代前沿 | `#0170C1` | 同主色 | `reference/style4-tech-modern.md` |
| 5 | 自定义 | 从 style-custom.md 提取 | | `reference/style-custom.md` |

- **论文答辩**：用户未指定时默认风格 1
- **通用汇报**：用户选择或根据语境自动推荐

### Step 2：生成多页 Draw.io XML

**必须先读取所选风格的 reference 文件**，基于该风格生成 XML。

- 画布：16:9（pageWidth=1920，pageHeight=1080）
- 页序：按模式识别表中的默认页序
- 页数：10 分钟约 10-12 页，15 分钟约 14-18 页

### Step 3 & 4：输出 Draw.io 并自动导出 PPT

#### Step 3：输出 Draw.io 文件
将生成的 XML **一次性** 写入工作区 `.drawio` 文件，并简述每页概要。

#### Step 4：自动导出 PPT（必执行）
生成 `.drawio` 后，执行导出：
1. 如未安装：`pip install drawio2pptx -q`
2. 切换到 `.drawio` 文件所在目录：
   ```bash
   Set-Location "d:\你的项目目录"
   drawio2pptx <文件名>.drawio <文件名>.pptx
   ```
3. 验证输出页数：输出中必须包含 `Saved xxx.pptx (N slides)`

### 其他注意事项
- **统一字号规则**：内容页中文正文统一使用 **18 pt**
- **字体推荐**：中文标题/正文优先使用 **微软雅黑** 或 **宋体**
- XML 标签正确闭合，特殊字符转义

---

## 10. create-skill - 创建技能

```yaml
---
name: create-skill
description: Guides users through creating effective Agent Skills for Cursor. Use when the user wants to create, write, or author a new skill, or asks about skill structure, best practices, or SKILL.md format.
---
```

### Before You Begin: Gather Requirements

Before creating a skill, gather essential information from the user about:
1. **Purpose and scope**: What specific task or workflow should this skill help with?
2. **Target location**: Should this be a personal skill (~/.cursor/skills/) or project skill (.cursor/skills/)?
3. **Trigger scenarios**: When should the agent automatically apply this skill?
4. **Key domain knowledge**: What specialized information does the agent need?
5. **Output format preferences**: Are there specific templates, formats, or styles required?
6. **Existing patterns**: Are there existing examples or conventions to follow?

### Skill File Structure

#### Directory Structure
```
skill-name/
├── SKILL.md              # Required - main instructions
├── reference.md          # Optional - detailed documentation
├── examples.md           # Optional - usage examples
└── scripts/              # Optional - utility scripts
    ├── validate.py
    └── helper.sh
```

#### SKILL.md Structure

Every skill requires a `SKILL.md` file with YAML frontmatter and markdown body:

```markdown
---
name: your-skill-name
description: Brief description of what this skill does and when to use it
---

# Your Skill Name

## Instructions
Clear, step-by-step guidance for the agent.
```

### Writing Effective Descriptions

The description is **critical** for skill discovery. The agent uses it to decide when to apply your skill.

Best practices:
1. **Write in third person**
2. **Be specific and include trigger terms**
3. **Include both WHAT and WHEN**

### Core Authoring Principles

1. **Concise is Key** - The context window is shared with conversation history
2. **Keep SKILL.md Under 500 Lines**
3. **Progressive Disclosure** - Put essential information in SKILL.md; detailed reference material in separate files
4. **Set Appropriate Degrees of Freedom**

### Common Patterns

- **Template Pattern** - Provide output format templates
- **Examples Pattern** - For skills where output quality depends on seeing examples
- **Workflow Pattern** - Break complex operations into clear steps with checklists
- **Conditional Workflow Pattern** - Guide through decision points
- **Feedback Loop Pattern** - For quality-critical tasks, implement validation loops

---

## 11. skill-prompt-convert - Skill 与 Prompt 互转

```yaml
---
name: skill-prompt-convert
description: 在 Skill（SKILL.md）与 Prompt（聊天框指令）两种格式之间相互转换。支持 Skill→Prompt 与 Prompt→Skill 双向转换，保持核心信息零丢失。当用户提到 Skill 转 Prompt、Prompt 转 Skill、格式互转、SKILL.md 转换时使用。
---
```

### 使用时机

- 用户需要将 Skill 转为可直接复制到聊天框的 Prompt
- 用户需要将 Prompt 转为 SKILL.md 格式的 Skill
- 用户提到 Skill 与 Prompt 互转、格式转换

### Step 1：获取输入并确认方向

从用户消息或粘贴/附件中获取待转换内容，判断方向：
- **A. Skill → Prompt**：输入为 SKILL.md 内容，输出聊天框可用的 Prompt
- **B. Prompt → Skill**：输入为 Prompt 内容（含 ``` 代码块），输出 SKILL.md 格式

### Step 2：执行转换

**Skill → Prompt 时**：将 `name`、`description` 融入 `# Role` 和 `# Task`；将「使用时机」转化为适用场景；将 Step 1/2... 转化为 `# Workflow` 或 `# Constraints`；补充 `# Output Format` 和 `# Input` 占位符；输出用 ``` 包裹。

**Prompt → Skill 时**：从 `# Role`、`# Task` 提炼 `name`（英文小写短横线）和 `description`；从 `# Task` 或 `# Constraints` 提炼「使用时机」；将 `# Workflow`、`# Constraints` 拆解为 Step 1、Step 2...；保留 `# Output Format` 到「注意事项」；输出完整 SKILL.md，**必须符合标准 Skill 格式**。

### Step 3：输出结果

- **Part 1 [转换说明]**：简要说明映射关系
- **Part 2 [转换结果]**：完整的转换后内容

### 注意事项

- **信息零丢失**：不得删减核心逻辑、步骤、约束条件
- **格式适配**：Skill 强调「何时触发」「Agent 如何执行」；Prompt 强调「用户输入什么」「输出什么格式」
- **命名规范**：`name` 必须英文、小写、短横线
- **标准 Skill 格式**：YAML 前置元数据必须用 `---` 开头和结尾闭合

---

## 12. wechat-article-writer - 公众号/自媒体创作

```yaml
---
name: wechat-article-writer
description: 公众号/自媒体全流程。根据用户表述自动匹配：撰写文章、封面图、正文插图、风格提取。支持多种写作风格。当用户提到写公众号、技术博客、公众号封面、正文插图、步骤图、演示图、流程示意、分析写作风格、克隆文风、模仿爆款、提取风格时使用。详见 reference 目录。
---
```

### 一、任务识别

| 任务类型 | 触发词 | 执行 |
| ------- | ----------------------------- | ----------------------------------------------------------- |
| 仅封面/结尾图 | 封面图、公众号封面、B站封面、小红书配图 | 读取 [cover_guide.md](reference/cover_guide.md) |
| 仅正文插图 | 插图、步骤图、演示图、流程示意、前后对比 | 读取 [illustration_guide.md](reference/illustration_guide.md) |
| 撰写文章 | 写公众号、写文章、自媒体写作、爆款文章、内容创作 | 执行 Step 2–6 |
| 风格提取 | 分析写作风格、克隆文风、模仿某篇、提取风格、范文转风格指南 | 执行「四、风格提取流程」 |

### 二、写作风格

| 序号 | 风格 | 触发词 | 参考文件 | 篇幅 |
| --- | -------- | ------------------ | ------------------------------------------------------------------------------ | ----------- |
| 1 | 默认 | （未指定时） | [writing_style.md](reference/writing_style.md) | 2000–4000 字 |
| 2 | 高流量/爆款 | 高流量、爆款、像 Skills 那篇 | [viral_style.md](reference/viral_style.md) | 2500–4000 字 |
| 3 | 清单体/方法论 | 清单体、方法论、干货、步骤 | [checklist_methodology_style.md](reference/checklist_methodology_style.md) | 2000–4000 字 |
| 4 | 资源盘点 | 盘点、替代方案、合集 | [resource_roundup_style.md](reference/resource_roundup_style.md) | 3000–6000 字 |
| 5 | 个人实测推荐 | 个人实测、亲身推荐 | [personal_tool_review_style.md](reference/personal_tool_review_style.md) | 4000–7000 字 |
| 6 | 认知颠覆 | 认知颠覆、反常识、观点文 | [contrarian_opinion_style.md](reference/contrarian_opinion_style.md) | 2000–3500 字 |
| 7 | 身份共鸣/逆袭 | 身份共鸣、逆袭、你也行、转行经历 | [identity_transformation_style.md](reference/identity_transformation_style.md) | 2500–4000 字 |
| 8 | 故事化/情感共鸣 | 故事化、情感共鸣、人物故事 | [story_emotional_style.md](reference/story_emotional_style.md) | 2500–4500 字 |
| 9 | 深度随笔 | 深度思考、随笔、像日记那篇、个人感悟 | [personal_essay_style.md](reference/personal_essay_style.md) | 4000–7000 字 |

### 三、撰写流程（Step 2–6）

#### Step 2：搜索资料
- 并行搜索多来源（官方文档、X/Twitter、Reddit、技术论坛等）
- 优先当月/当季最新资料
- 深度总结后再进入撰写

#### Step 3：撰写文章
1. **读取风格文件**：按「二、写作风格」选择对应 reference 文件，严格遵循其写作规范与结尾语
2. **通用要求**：故事化开头、带情感色彩、准备 2–3 个备选标题

#### Step 4：生成标题
生成 5 个爆款风格标题：痛点明确、数字吸引、结果导向、情绪调动、悬念设置。

#### Step 5：排版优化
输出排版与配图建议：段落结构、配图位置（封面/正文/结尾）、代码块留白、金句单独成段。

#### Step 6：生成配图（可选）
用户要求或排版建议中标注配图时：
1. **读取指南**
2. **生成并保存 .drawio 文件**
3. **自动转换为 PNG（可选）**
4. **输出使用说明**

#### Step 7：上传到微信公众号（可选）
用户要求上传到草稿箱时执行，支持手动和自动两种模式。

### 四、风格提取流程

当用户提供样本文章（全文粘贴或本地路径），希望分析风格、克隆文风、将范文转为风格指南时执行。

**先读取** [extraction_dimensions.md](reference/extraction_dimensions.md)，按统一维度提取。

1. **Step 1：任务确认**
2. **Step 2：结构拆解**
3. **Step 3：语言与修辞拆解**
4. **Step 4：产出风格规则包**
5. **Step 5：验证与回放（可选）**

---

## 附录：技能索引

| 序号 | 技能名称 | 功能描述 |
| --- | -------- | -------- |
| 1 | codegen-diagram | 基于当前项目/代码生成 Draw.io 图表（技术栈图、系统架构图、数据结构图、E-R 图） |
| 2 | codegen-doc | 基于当前项目/代码生成各类文档（论文章节、项目梳理、重点问题、简历项目描述） |
| 3 | dev-workflow | 开发流程五步法（需求理解、方案设计、代码实现、代码审查、Bug 修复） |
| 4 | drawio-diagram | 生成标准 Draw.io 格式图表（从零生成与风格迁移两种模式） |
| 5 | excalidraw-diagram | 生成可直接在 Excalidraw 中打开的手绘风图表 |
| 6 | frontend-design | 创建具有高设计品质、可交付生产的前端界面 |
| 7 | md-report-summary | 生成高质量 Markdown 周报、工作汇报、总结、介绍等文档 |
| 8 | paper-write | 本科与硕士学位论文全流程撰写辅助 |
| 9 | pptgen-drawio | 根据论文或汇报内容生成多页 Draw.io 格式 PPT |
| 10 | create-skill | 指导用户创建有效的 Agent Skills |
| 11 | skill-prompt-convert | 在 Skill（SKILL.md）与 Prompt（聊天框指令）两种格式之间相互转换 |
| 12 | wechat-article-writer | 公众号/自媒体全流程创作（撰写文章、封面图、正文插图、风格提取） |
