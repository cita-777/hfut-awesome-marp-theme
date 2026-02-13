---
name: hfut-marp-slides
description: Use when creating Marp presentation slides, especially for HFUT academic defense, course reports, or thesis presentations. Triggers on keywords like PPT, slides, Marp, presentation, 答辩, 汇报, 演示文稿. When a project codebase folder exists in the PPT workspace, enforces strict fact-based content generation from actual source code analysis.
---

# HFUT Awesome Marp Slides

## Overview

使用 HFUT Awesome Marp 主题快速创建专业的学术演示文稿。基于 Markdown 语法，支持多种布局、导航栏、代码高亮、数学公式等特性。

## 工程目录分析（Project-Aware Mode）

**当用户的 PPT 工作目录中存在工程项目文件夹时，PPT 内容必须严格基于工程事实。**

### 检测条件

生成 PPT 前，先扫描 PPT 工作目录（即用户指定的 `ws_src/xxx/` 目录）下是否存在工程项目文件夹。识别标志：

| 标志文件 | 语言/框架 |
|----------|-----------|
| `Cargo.toml` | Rust |
| `package.json` | Node.js / 前端 |
| `go.mod` | Go |
| `pom.xml` / `build.gradle` | Java |
| `CMakeLists.txt` / `Makefile` | C/C++ |
| `pyproject.toml` / `setup.py` / `requirements.txt` | Python |
| `*.sln` / `*.csproj` | C# / .NET |

**如果检测到任何一个标志文件，立即进入 Project-Aware Mode。**

### Project-Aware Mode 工作流

```
检测到工程文件夹
  ↓
Step 1: 深度代码分析（必须先完成，再写任何 PPT 内容）
  ↓
Step 2: 建立事实清单（Fact Sheet）
  ↓
Step 3: 基于事实清单生成 PPT 内容
  ↓
Step 4: 逐页交叉验证
```

### Step 1: 深度代码分析（强制）

**在写任何一行 PPT 内容之前，必须完成以下分析：**

1. **读取项目元数据** — `Cargo.toml` / `package.json` / `go.mod` 等，提取：
   - 项目名称、版本、作者、描述
   - **所有依赖及其版本号**（直接依赖，非传递依赖）
   - 构建配置、feature flags

2. **读取所有源代码文件** — 逐个读取 `src/`、`lib/`、`app/` 等目录下的每一个源文件，提取：
   - 模块结构和文件组织
   - 核心数据结构（struct、class、interface 定义）
   - API 端点 / 路由定义
   - 关键算法和业务逻辑
   - 错误处理方式

3. **读取配置文件** — `config/`、`.env`、`*.yaml`、`*.toml` 等
4. **读取测试文件** — `tests/`、`*_test.*`、`*.spec.*`
5. **读取文档** — `README.md`、`docs/`

**硬性禁止：未读取的文件中的内容不得出现在 PPT 中。**

### Step 2: 建立事实清单

分析完成后，在生成 PPT 前必须先整理出事实清单（不写入文件，在生成过程中作为内部参照）：

```
事实清单示例：
- 项目名：webserver
- 语言：Rust 2021 Edition
- 核心依赖：tokio 1.36.0, serde 1.0.197, flate2 1.0.28, brotli 3.5.0, ...
- 模块：main.rs, request.rs, response.rs, config.rs, cache.rs, param.rs, util.rs, exception.rs
- 支持的 HTTP 方法：GET, HEAD, OPTIONS（代码依据：param.rs 中 ALLOWED_METHODS）
- 压缩算法：Gzip, Deflate, Brotli（代码依据：response.rs 中 compress 逻辑）
- 缓存策略：FIFO（代码依据：cache.rs 中 FileCache 实现）
- ...
```

**每一条事实必须标注代码依据（文件名 + 具体位置）。**

### Step 3: 严格事实约束规则

**以下规则在 Project-Aware Mode 下为强制执行，违反任何一条都是不可接受的：**

| 规则 | 说明 | 违反示例 |
|------|------|----------|
| **禁止编造技术栈** | 所有技术栈必须来自依赖文件 | 项目没用 Redis 却写"使用 Redis 缓存" |
| **禁止编造功能** | 只写代码中实际实现的功能 | 代码没有 HTTPS 却写"支持 TLS 加密" |
| **禁止编造架构** | 架构描述必须与代码模块结构一致 | 代码是单体却写"微服务架构" |
| **禁止编造性能数据** | 性能数据必须来自项目文档/README | 没有 benchmark 却写"QPS 达到 10 万" |
| **禁止美化描述** | 不得将简单实现描述为复杂高级方案 | FIFO 缓存却写"智能缓存淘汰策略" |
| **代码展示必须真实** | PPT 中的代码片段必须从源码中提取精简 | 不得凭空编写"示例代码" |
| **禁止推测设计意图** | 只描述代码做了什么，不猜测为什么 | 不得写"考虑到高并发场景特别设计了..." |

### Step 4: 代码片段引用规范

**PPT 中展示代码时：**

1. **必须从实际源码中提取** — 可以精简（删除非关键行），但不能改变逻辑
2. **标注来源** — 在代码块上方或旁边说明来自哪个文件
3. **精简规则** — 提取核心逻辑，删除 import、日志、注释等非关键行，控制在 8 行以内（两栏）或 10 行以内（单栏）
4. **禁止凭空编写** — 不得为了"演示效果"编写项目中不存在的代码

### 无工程目录时的行为

如果 PPT 工作目录下没有检测到任何工程项目文件夹，则按照用户提供的文字描述正常生成 PPT，不受上述约束。

## Quick Start

### 1. YAML Front Matter（必须）

```yaml
---
marp: true
size: 16:9
theme: am_red          # 可选: am_red, am_blue, am_green, am_purple, am_brown, am_dark
paginate: true
headingDivider: [2,3]  # 二级/三级标题自动分页
footer: \ *作者名* *班级* *日期*
---
```

### 2. 基础结构

```
封面页 (cover_e)
  ↓
目录页 (toc_b)
  ↓
[章节过渡页 (trans) → 内容页 (navbar + 布局)] × N
  ↓
结束页 (lastpage)
```

## Page Types Reference

### 封面页

| Class | 特点 | 适用场景 |
|-------|------|----------|
| `cover_e` | 左白右色三角，右上角校徽 | **最常用**，答辩/汇报 |
| `cover_a` | 上色下白渐变，居中标题 | 简洁风格 |
| `cover_b` | 圆角矩形标题框 | 突出标题 |
| `cover_c` | 横向色带，左对齐 | 正式场合 |
| `cover_d` | 上色带下白 | 简约风格 |

**cover_e 示例（推荐）：**

```markdown
<!-- _class: cover_e -->
<!-- _paginate: "" -->
<!-- _footer: ![](../hfut-badge/HFUT_Horizontal_name&badge_white.png) -->
<!-- _header: ![](../hfut-badge/HFUT_badge_white.png) -->

# 演示文稿标题

###### 副标题说明

汇报人：姓名
班级信息
```

### 目录页

```markdown
<!-- _header: 目录<br>CONTENTS<br>![](../hfut-badge/HFUT_badge_white.png)-->
<!-- _class: toc_b -->
<!-- _footer: "" -->
<!-- _paginate: "" -->

- [第一章标题](#页码)
- [第二章标题](#页码)
- [第三章标题](#页码)
```

### 章节过渡页

```markdown
## 1. 章节标题

<!-- _class: trans -->
<!-- _footer: "" -->
<!-- _paginate: "" -->
```

### 内容页（navbar + 布局）

```markdown
## 1.1 小节标题
<!-- _header: \ ***文档标题*** **当前章节** *其他章节* *其他章节*-->
<!-- _class: navbar cols-2 fglass -->

<div class=ldiv>
左栏内容
</div>

<div class=rdiv>
右栏内容
</div>
```

**导航栏语法：** `***粗斜体***` 文档标题 | `**粗体**` 当前章节 | `*斜体*` 其他章节

### 结束页

```markdown
<!-- _class: lastpage -->
<!-- _footer: "" -->
![ ](../hfut-badge/HFUT_Horizontal_name&badge.svg)
###### 感谢观看！
```

## Layout Classes

### 两栏布局

| Class | 比例 | div类 |
|-------|------|-------|
| `cols-2` | 50%-50% | `ldiv/rdiv` 或 `limg/rimg` |
| `cols-2-64` | 60%-40% | 同上 |
| `cols-2-46` | 40%-60% | 同上 |
| `cols-2-73` | 70%-30% | 同上 |
| `cols-2-37` | 30%-70% | 同上 |

### 其他布局

| Class | 说明 | div类 |
|-------|------|-------|
| `cols-3` | 三栏 | `ldiv/mdiv/rdiv` |
| `rows-2` | 两行 | `tdiv/bdiv` |
| `pin-3` | 品字型 | `tdiv` + `ldiv/rdiv` |

**布局选择原则：**
- `pin-3` 要求三个区域都有充足内容（每区至少 3-4 行文字），否则大量留白很丑
- 内容较少时优先用 `cols-2` 或 `cols2_ol_ci`
- `timg` 不要只放一行标题——应放实质性内容（完整段落、带详细说明的引用块）
- 总结/展望类页面通常内容偏少，**优先选 `cols-2 fglass` 而非 `pin-3`**

**div 后缀说明：**
- `ldiv/rdiv/mdiv/tdiv/bdiv`: 普通容器
- `limg/rimg/mimg/timg/bimg`: 内容居中（适合图片）

## Style Classes

### 列表样式（可叠加）

| Class | 效果 |
|-------|------|
| `col1_ol_sq` | 单列有序+方形序号 |
| `col1_ol_ci` | 单列有序+圆形序号 |
| `cols2_ol_sq` | 两列有序+方形序号 |
| `cols2_ol_ci` | 两列有序+圆形序号 |
| `cols2_ul_sq` | 两列无序+方形 |
| `cols2_ul_ci` | 两列无序+圆形 |

### 引用框颜色

| Class | 颜色 | 适用 |
|-------|------|------|
| `bq-blue` | 蓝色 | 信息说明 |
| `bq-red` | 红色 | 警告/重要 |
| `bq-green` | 绿色 | 成功/正面 |
| `bq-purple` | 紫色 | 提示 |
| `bq-black` | 黑色 | 严肃内容 |

### 字体大小

| Class | 倍率 |
|-------|------|
| `tinytext` | 0.8x |
| `smalltext` | 0.9x |
| `largetext` | 1.15x |
| `hugetext` | 1.3x |

### 其他样式

| Class | 效果 |
|-------|------|
| `fglass` | 毛玻璃效果列表框 |
| `fixedtitleA` | 固定标题（上对齐） |
| `fixedtitleB` | 固定标题+底色背景 |
| `footnote` | 脚注样式 |
| `caption` | 图表标题 |

## Image Syntax

```markdown
![](img.png)              # 普通图片
![#c](img.png)            # 居中
![w:500](img.png)         # 宽度500px
![h:300](img.png)         # 高度300px
![#c w:500](img.png)      # 居中+宽度
![#c h:400](img.png)      # 居中+高度
```

### 图片占位符（重要）

**生成 PPT 时图片往往还不存在，使用占位符模式：**

```markdown
## 小节标题
<!-- _class: navbar caption -->

<div class=rimg>

<!-- TODO: 替换为实际图片 img/architecture.png -->
![#c h:400](img/placeholder.png)

<div class="caption">
图1：系统架构图
</div>

</div>
```

**占位符规范：**
- 使用 `<!-- TODO: 替换为实际图片 img/xxx.png -->` 注释标记
- 图片路径使用有意义的名称（如 `architecture.png`）
- **必须写好 caption**，说明图片内容
- 用户后续只需替换图片文件，无需改代码

**图表标题（关键）：**
- **必须在 `_class` 中加 `caption`** 才能渲染 `<div class="caption">` 的样式
- 例如 `<!-- _class: navbar cols-2 fglass caption -->`

```markdown
<!-- _class: navbar caption -->

![#c h:400](img/diagram.png)

<div class="caption">
图1：系统架构图
</div>
```

## 单页内容上限（必读）

**Marp 不会自动分页。内容超出页面会被裁切并覆盖脚注。必须严格控制每页内容量。**

### 每页最大内容量

| 页面类型 | 上限 | 示例 |
|----------|------|------|
| 单栏 | 正文总计 **≤10 行** | 1 个表格(≤5数据行) + 标题 + 引用块 |
| 两栏 (cols-2) | 每栏 **≤8 行** | 标题 + 列表(≤5项) 或 标题 + 小表格 |
| 含代码（单栏） | 代码 **≤10 行** | 标题 + 代码块 + 简短说明 |
| 含代码（两栏） | 代码 **≤8 行** | 标题 + 代码块 |

**行数计算**：标题行 + 列表项数 + 表格行数(含表头) + 代码行数 + 引用行数 = 总行数

### 硬性禁止

- **同一页面或同一栏禁止放两个表格** — 几乎 100% 溢出
- **两栏代码禁止超过 8 行** — 超出必须精简或拆页
- **单栏代码禁止超过 10 行** — 超出必须精简或拆页

### 超出时如何拆页

将一页拆为两页，**保持同一小节编号**，用短横线加子标题区分：

```
## 3.2 Neo4j 存储 - 数据模型    ← 第一页
## 3.2 Neo4j 存储 - 查询示例    ← 第二页
```

### 写完每页必须验证

**每写完一页，立即执行以下检查：**

1. 数总行数（标题 + 列表 + 表格 + 代码 + 引用）
2. 单栏 > 10 行 → **必须拆页**
3. 两栏任一栏 > 8 行 → **必须拆页**
4. 出现两个表格 → **必须拆页**
5. 宁可多一页留白，也不要少一页溢出

## Best Practices

### 图片工作流（重要）

**先写结构，后加图片：**

1. **生成阶段** — 使用占位符 `<!-- TODO: 替换为实际图片 -->` + 写好 caption
2. **用户准备图片** — 根据 caption 说明准备对应图片
3. **替换阶段** — 将图片放入 `img/` 文件夹，删除 TODO 注释

**图片数量要求：**
- 一份 20+ 页的 PPT 至少包含 **5-6 张图片占位符**
- 适合放图的位置：整体架构图、数据流/流程图、实验结果图、系统截图/演示图、对比可视化图
- 图片页通常用 `cols-2-64 caption` 或单栏 `caption` 布局，图片放在 `rimg` 或独立居中

**为什么这样做：**
- 纯文字 PPT 信息密度高但视觉单调，图片提升表达力
- 生成时图片通常不存在，用占位符标记
- caption 先写好确保图片内容明确
- 用户只需替换文件，不需要改代码

### 页面组织

1. **每章开头用 trans 过渡页** — 给观众清晰的章节切换信号
2. **navbar 保持一致** — 同一章节内用相同的 header 导航
3. **合理使用 fglass** — 列表内容配合毛玻璃效果更美观

### 内容布局

1. **图文并排用 cols-2-64 或 cols-2-46** — 文字多的一侧占大比例
2. **代码展示用 cols-2** — 左边代码，右边效果图/说明
3. **步骤说明用 col1_ol_ci + fglass** — 有序列表+圆形序号
4. **对比内容用表格** — 清晰展示差异
5. **总结/展望页用 cols-2 fglass 或 cols2_ol_ci** — 不要用 pin-3（内容通常不够填满三区域）
6. **引用框放实质内容** — `>` 引用块应包含总结性段落或详细说明，不要只写一行标题标签
7. **表格、列表、代码必须放 `ldiv/rdiv`，禁止放 `limg/rimg`** — `limg/rimg` 使用 flexbox 居中，会压缩表格宽度导致列被截断；`limg/rimg` 仅用于图片
8. **两栏高度尽量平衡** — 若一栏内容明显少于另一栏，在较短一栏补充引用块（`>`）或额外说明文字，避免底部大片留白

### 内容密度

1. **每个 div 区域至少 3-4 行实质内容** — 太少则留白过多，显得空洞
2. **列表项用"粗体关键词+冒号+说明"格式** — 如 `**知识蒸馏**：压缩模型体积，降低推理延迟`
3. **避免裸列表** — 只写三五个短词条的列表看起来很单薄，补充解释或加引用块充实内容
4. **内容上限和拆页规则** — 见上方「单页内容上限」章节，**每页写完必须验证行数**

### 技术内容

1. **代码块指定语言** — ` ```verilog ` ` ```python ` 等
2. **关键代码配合说明** — 先文字解释，再代码展示
3. **波形/架构图配 caption** — 标注图号和说明

### 信息密度

1. **每页一个核心观点** — 不要堆砌信息
2. **超过5条用两列布局** — cols2_ol_ci 或 cols2_ul_ci
3. **文字过多用 tinytext/smalltext** — 保持可读性

## Template: Academic Defense

```markdown
---
marp: true
size: 16:9
theme: am_red
paginate: true
headingDivider: [2,3]
footer: \ *姓名* *班级* *日期*
---

<!-- _class: cover_e -->
<!-- _paginate: "" -->
<!-- _footer: ![](../hfut-badge/HFUT_Horizontal_name&badge_white.png) -->
<!-- _header: ![](../hfut-badge/HFUT_badge_white.png) -->

# 论文/项目标题

###### 副标题（课程名称/竞赛名称）

汇报人：姓名
指导老师：老师姓名

---

<!-- _header: 目录<br>CONTENTS<br>![](../hfut-badge/HFUT_badge_white.png)-->
<!-- _class: toc_b -->
<!-- _footer: "" -->
<!-- _paginate: "" -->

- [研究背景](#3)
- [方案设计](#N)
- [实现细节](#N)
- [实验验证](#N)
- [总结展望](#N)

## 1. 研究背景

<!-- _class: trans -->
<!-- _footer: "" -->
<!-- _paginate: "" -->

## 1.1 问题描述
<!-- _header: \ ***答辩标题*** **研究背景** *方案设计* *实现细节* *实验验证* *总结*-->
<!-- _class: navbar cols-2 fglass -->

<div class=ldiv>

**背景说明**

- 要点1
- 要点2
- 要点3

</div>

<div class=rimg>

<!-- TODO: 替换为实际图片 img/background.png -->
![#c h:400](img/background.png)

<div class="caption">
图1：问题示意图
</div>

</div>

<!-- 更多内容页... -->

## N. 未来展望
<!-- _header: \ ***答辩标题*** *研究背景* *方案设计* *实现细节* *实验验证* **总结**-->
<!-- _class: navbar cols-2 fglass bq-blue -->

<div class=ldiv>

**方向一标题**

- **关键词A**：具体说明，解释做什么、为什么
- **关键词B**：具体说明
- **关键词C**：具体说明

> 小结或目标说明

</div>

<div class=rdiv>

**方向二标题**

- **关键词D**：具体说明
- **关键词E**：具体说明
- **关键词F**：具体说明

> 小结或目标说明

</div>

---

<!-- _class: lastpage -->
<!-- _footer: "" -->
![ ](../hfut-badge/HFUT_Horizontal_name&badge.svg)
###### 感谢观看！
```

## Common Mistakes

| 错误 | 正确做法 |
|------|----------|
| 忘记 `<!-- _paginate: "" -->` 在封面/目录 | 特殊页面记得隐藏页码 |
| div 类名拼错（如 `ldvi`） | 检查 `ldiv/rdiv/limg/rimg` |
| 图片路径错误 | 使用相对路径 `img/xxx.png` |
| navbar 语法错误 | 注意 `\` 开头，星号数量 |
| class 组合顺序 | navbar 放前面，布局放后面 |
| 忘记 fglass | 列表内容加 fglass 更美观 |
| pin-3 内容太少，大量留白 | pin-3 每个区域需 3-4 行以上，否则换用 cols-2 |
| `>` 引用块只写一行标题 | 引用块应包含实质段落，不要当标签用 |
| 列表项太短太裸 | 用 `**关键词**：说明` 格式充实每一条 |
| 内容超出页面被裁切 | 宁可拆成两页，不要硬挤。单栏 ≤12 行，每栏 ≤10 行 |
| 同一页/栏放两个表格 | 几乎必然溢出，必须拆成两页 |
| 两栏中代码块超过 8 行 | 两栏代码 ≤8 行，单栏 ≤10 行 |
| `<div class="caption">` 无效果 | 必须在 `_class` 中加 `caption` 才能渲染图注样式 |
| 两栏表格放在 `limg/rimg` 中 | `limg/rimg` 是 flexbox 居中，会压缩表格列宽导致截断；表格必须用 `ldiv/rdiv` |
| 两栏高度严重不平衡，底部大片留白 | 较短一栏补充引用块或说明文字平衡高度 |
| 有工程目录却编造技术栈/功能 | 必须先深度分析代码，所有内容基于事实清单 |
| 代码片段是凭空编写的 | 必须从实际源码提取精简，标注来源文件 |
| 写了项目未实现的功能 | 只描述代码中确实存在的功能，不美化不推测 |

## File Organization

```
your-ppt/
├── hfut-awesome-marp.md    # 主文件
├── img/                     # 图片文件夹
│   ├── architecture.png
│   ├── result1.png
│   └── ...
└── your-project/            # [可选] 工程项目文件夹
    ├── Cargo.toml / package.json / ...
    ├── src/
    └── ...
```

**图片命名建议：** 使用有意义的名称如 `architecture.png`、`workflow.png`，而非 `image1.png`

**工程目录说明：** 如果用户在 PPT 目录下放入了工程项目文件夹，自动进入 Project-Aware Mode（见上方「工程目录分析」章节）
