---
marp: true
size: 16:9
theme: am_blue
paginate: true
headingDivider: [2,3]
footer: \ *张三* *计算机科学与技术23-1班* *2026/02/13*
---

<!-- _class: cover_e -->
<!-- _paginate: "" -->
<!-- _footer: ![](../hfut-badge/HFUT_Horizontal_name&badge_white.png) -->
<!-- _header: ![](../hfut-badge/HFUT_badge_white.png) -->

# HFUT Marp 主题功能演示

###### Skill 效果测试 · 全特性展示

演示人：张三
计算机科学与技术 23-1 班
指导老师：李四 教授

---

<!-- _header: 目录<br>CONTENTS<br>![](../hfut-badge/HFUT_badge_white.png)-->
<!-- _class: toc_b -->
<!-- _footer: "" -->
<!-- _paginate: "" -->

- [布局展示](#3)
- [样式特性](#8)
- [内容元素](#13)
- [综合应用](#18)

## 1. 布局展示

<!-- _class: trans -->
<!-- _footer: "" -->
<!-- _paginate: "" -->

## 1.1 两栏均分布局 cols-2
<!-- _header: \ ***功能演示*** **布局展示** *样式特性* *内容元素* *综合应用*-->
<!-- _class: navbar cols-2 fglass -->

<div class=ldiv>

**左栏内容**

- **cols-2**：50%-50% 均分两栏
- **ldiv/rdiv**：普通文字容器
- **limg/rimg**：内容居中容器

> 适用于内容量相当的并排对比场景

</div>

<div class=rdiv>

**右栏内容**

- **fglass**：毛玻璃效果
- **navbar**：顶部导航栏
- **headingDivider**：自动分页

> 多个 class 可以自由组合叠加使用

</div>

## 1.2 两栏非均分布局 cols-2-64
<!-- _header: \ ***功能演示*** **布局展示** *样式特性* *内容元素* *综合应用*-->
<!-- _class: navbar cols-2-64 fglass bq-blue caption -->

<div class=ldiv>

**60% 宽度的主内容区**

- **cols-2-64**：左 60% 右 40%
- **cols-2-46**：左 40% 右 60%
- **cols-2-73**：左 70% 右 30%
- **cols-2-37**：左 30% 右 70%

> 当图文并排时，文字多的一侧应占大比例，保证可读性

</div>

<div class=rimg>

<!-- TODO: 替换为实际图片 img/layout-demo.png -->
![#c h:350](img/layout-demo.png)

<div class="caption">
图1：非均分布局效果示意
</div>

</div>

## 1.3 品字型布局 pin-3
<!-- _header: \ ***功能演示*** **布局展示** *样式特性* *内容元素* *综合应用*-->
<!-- _class: navbar pin-3 fglass -->

<div class=tdiv>

> **品字型布局**：上方一个区域横跨全宽，下方左右两个区域并排。适合"总—分"结构，每个区域都需要 3-4 行以上内容，否则留白过多。

</div>

<div class=ldiv>

**左下区域**

- **tdiv**：顶部区域
- **ldiv**：左下区域
- **rdiv**：右下区域

</div>

<div class=rdiv>

**右下区域**

- 三区域都要有充足内容
- 内容少时优先用 cols-2
- 总结页慎用 pin-3

</div>

## 1.4 三栏与两行布局
<!-- _header: \ ***功能演示*** **布局展示** *样式特性* *内容元素* *综合应用*-->
<!-- _class: navbar cols-3 fglass -->

<div class=ldiv>

**三栏布局**

cols-3 将页面分为三等分，使用 ldiv / mdiv / rdiv

</div>

<div class=mdiv>

**中栏内容**

适合展示三个并列概念或三组对比数据

</div>

<div class=rdiv>

**右栏内容**

每栏空间有限，内容需精简控制

</div>

## 2. 样式特性

<!-- _class: trans -->
<!-- _footer: "" -->
<!-- _paginate: "" -->

## 2.1 有序列表样式
<!-- _header: \ ***功能演示*** *布局展示* **样式特性** *内容元素* *综合应用*-->
<!-- _class: navbar cols2_ol_ci fglass -->

1. **圆形序号样式**：col1_ol_ci / cols2_ol_ci
2. **方形序号样式**：col1_ol_sq / cols2_ol_sq
3. **两列自动分布**：cols2 前缀自动排列
4. **单列集中展示**：col1 前缀单列显示
5. **无序圆形样式**：cols2_ul_ci
6. **无序方形样式**：cols2_ul_sq

## 2.2 引用框颜色
<!-- _header: \ ***功能演示*** *布局展示* **样式特性** *内容元素* *综合应用*-->
<!-- _class: navbar cols-2 -->

<div class=ldiv>

**蓝色引用 bq-blue**

> 适合展示信息说明、背景介绍、客观描述等中性内容

**红色引用 bq-red**

> 适合展示警告、重要提示、关键注意事项等需要强调的内容

</div>

<div class=rdiv>

**绿色引用 bq-green**

> 适合展示成功案例、正面结果、优势亮点等积极内容

**紫色引用 bq-purple**

> 适合展示提示信息、补充说明、扩展知识等辅助内容

</div>

## 2.3 毛玻璃与固定标题
<!-- _header: \ ***功能演示*** *布局展示* **样式特性** *内容元素* *综合应用*-->
<!-- _class: navbar cols-2 fglass bq-blue -->

<div class=ldiv>

**毛玻璃效果 fglass**

- 为列表项添加半透明背景
- 增强内容层次感与视觉美观
- 与任何布局 class 自由组合

> fglass 是最常用的装饰 class 之一

</div>

<div class=rdiv>

**固定标题样式**

- **fixedtitleA**：标题上对齐固定
- **fixedtitleB**：标题带底色背景
- 适合标题需要突出的场景

> 固定标题可搭配各种布局使用

</div>

## 2.4 字体大小调节
<!-- _header: \ ***功能演示*** *布局展示* **样式特性** *内容元素* *综合应用*-->
<!-- _class: navbar col1_ol_ci fglass -->

1. **tinytext**：0.8 倍字号，适合内容密集页面
2. **smalltext**：0.9 倍字号，微调内容空间
3. **默认字号**：标准大小，适合大多数场景
4. **largetext**：1.15 倍字号，突出重要内容
5. **hugetext**：1.3 倍字号，用于标题强调

## 3. 内容元素

<!-- _class: trans -->
<!-- _footer: "" -->
<!-- _paginate: "" -->

## 3.1 表格展示
<!-- _header: \ ***功能演示*** *布局展示* *样式特性* **内容元素** *综合应用*-->
<!-- _class: navbar fglass -->

| 主题名称 | 主色调 | 适用场景 |
|---------|--------|---------|
| am_red | 红色（HFUT 校色） | 答辩、正式汇报 |
| am_blue | 蓝色 | 技术报告、学术交流 |
| am_green | 绿色 | 环境、生态相关 |
| am_purple | 紫色 | 创意、设计展示 |
| am_brown | 棕色 | 人文、历史主题 |
| am_dark | 深色 | 夜间演示、科技感 |

## 3.2 代码块展示
<!-- _header: \ ***功能演示*** *布局展示* *样式特性* **内容元素** *综合应用*-->
<!-- _class: navbar cols-2 fglass -->

<div class=ldiv>

**Python 示例**

```python
def fibonacci(n: int) -> list:
    fib = [0, 1]
    for i in range(2, n):
        fib.append(fib[-1] + fib[-2])
    return fib[:n]
```

> 代码块自动语法高亮，指定语言即可

</div>

<div class=rdiv>

**Rust 示例**

```rust
fn fibonacci(n: usize) -> Vec<u64> {
    let mut fib = vec![0, 1];
    for i in 2..n {
        let next = fib[i-1] + fib[i-2];
        fib.push(next);
    }
    fib.truncate(n); fib
}
```

</div>

## 3.3 数学公式
<!-- _header: \ ***功能演示*** *布局展示* *样式特性* **内容元素** *综合应用*-->
<!-- _class: navbar cols-2-64 fglass bq-purple -->

<div class=ldiv>

**Marp 支持 KaTeX 数学公式渲染**

行内公式：能量质量方程 $E = mc^2$

独立公式块：

$$\mathcal{L}(\theta) = -\frac{1}{N}\sum_{i=1}^{N}\left[y_i\log\hat{y}_i + (1-y_i)\log(1-\hat{y}_i)\right]$$

> 使用 LaTeX 语法书写公式，Marp 通过 KaTeX 引擎实时渲染

</div>

<div class=rdiv>

**常用公式示例**

$$\nabla \times \mathbf{E} = -\frac{\partial \mathbf{B}}{\partial t}$$

$$\int_{-\infty}^{\infty} e^{-x^2} dx = \sqrt{\pi}$$

</div>

## 3.4 图片与标题
<!-- _header: \ ***功能演示*** *布局展示* *样式特性* **内容元素** *综合应用*-->
<!-- _class: navbar cols-2-46 fglass caption -->

<div class=ldiv>

<!-- TODO: 替换为实际图片 img/architecture.png -->
![#c h:380](img/architecture.png)

<div class="caption">
图2：系统架构示意图
</div>

</div>

<div class=rdiv>

**图片语法要点**

- `![#c](img.png)` 居中显示
- `![w:500](img.png)` 指定宽度
- `![h:300](img.png)` 指定高度
- 组合使用：`![#c h:400](img.png)`

> 在 `_class` 中加入 `caption` 才能渲染 `<div class="caption">` 样式

</div>

## 4. 综合应用

<!-- _class: trans -->
<!-- _footer: "" -->
<!-- _paginate: "" -->

## 4.1 技术方案对比
<!-- _header: \ ***功能演示*** *布局展示* *样式特性* *内容元素* **综合应用**-->
<!-- _class: navbar cols-2 fglass bq-red -->

<div class=ldiv>

**方案 A：单体架构**

- **部署简单**：单一可执行文件
- **调试方便**：统一日志与调用栈
- **性能直接**：进程内函数调用

> 适合中小规模项目，团队规模 < 10 人

</div>

<div class=rdiv>

**方案 B：微服务架构**

- **独立部署**：各服务独立发布
- **技术多样**：各服务自选技术栈
- **弹性伸缩**：按需扩容单个服务

> 适合大规模项目，团队规模 > 20 人

</div>

## 4.2 实验数据展示
<!-- _header: \ ***功能演示*** *布局展示* *样式特性* *内容元素* **综合应用**-->
<!-- _class: navbar cols-2-64 fglass caption -->

<div class=ldiv>

**实验结果分析**

| 指标 | 优化前 | 优化后 |
|------|--------|--------|
| 响应时间 | 320ms | 45ms |
| 吞吐量 | 1.2k/s | 8.5k/s |
| 内存占用 | 512MB | 128MB |

> 经过缓存与索引优化后，各项指标均有显著提升

</div>

<div class=rimg>

<!-- TODO: 替换为实际图片 img/benchmark.png -->
![#c h:350](img/benchmark.png)

<div class="caption">
图3：优化前后性能对比
</div>

</div>

## 4.3 技术路线图
<!-- _header: \ ***功能演示*** *布局展示* *样式特性* *内容元素* **综合应用**-->
<!-- _class: navbar cols2_ol_ci fglass bq-green -->

1. **需求分析**：确定功能边界与非功能需求
2. **架构设计**：选择技术栈与系统拓扑
3. **核心开发**：实现业务逻辑与数据层
4. **测试验证**：单元测试、集成测试、压力测试
5. **部署上线**：CI/CD 流水线与监控告警
6. **迭代优化**：根据反馈持续改进

## 4.4 总结与展望
<!-- _header: \ ***功能演示*** *布局展示* *样式特性* *内容元素* **综合应用**-->
<!-- _class: navbar cols-2 fglass bq-blue -->

<div class=ldiv>

**已展示的特性**

- **多种布局**：cols-2/3、pin-3、rows-2
- **样式叠加**：fglass、bq-色、字号调节
- **内容元素**：表格、代码、公式、图片
- **页面类型**：封面、目录、过渡、导航

> 本演示涵盖了主题的核心功能模块

</div>

<div class=rdiv>

**进一步探索**

- **自定义主题色**：修改 SCSS 源文件
- **更多封面样式**：cover_a 到 cover_e
- **脚注与标注**：footnote class
- **响应式图片**：灵活的尺寸控制

> 详见项目 README 与 example 目录

</div>

---

<!-- _class: lastpage -->
<!-- _footer: "" -->
![ ](../hfut-badge/HFUT_Horizontal_name&badge.svg)
###### 感谢观看！
