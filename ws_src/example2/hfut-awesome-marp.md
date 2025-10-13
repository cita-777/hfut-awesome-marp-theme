---
marp: true
size: 16:9
theme: am_purple
paginate: true
headingDivider: [2,3]
footer: \ *Awesome Marp 语法示范* *计算机23-0班* *2025/10/13*
---



<!-- _class: cover_a -->
<!-- _header: "" --> 
<!-- _footer: "" --> 
<!-- _paginate: "" --> 

# HFUT Awesome Marp

###### 使用markdown简单快速制作ppt

![ h:60](../hfut-badge/HFUT_Horizontal_name&badge.svg)
汇报人：xxx
计算机23-0班
<2023xxxxxx@mail.hfut.edu.cn>


---


<!-- _class: cover_b -->
<!-- _header: "" -->
<!-- _footer: "" -->
<!-- _paginate: "" -->

# HFUT Awesome Marp

###### 使用markdown简单快速制作ppt

![ h:60](../hfut-badge/HFUT_Horizontal_name&badge.svg)
汇报人：xxx
计算机23-0班
<2023xxxxxx@mail.hfut.edu.cn>


---

<!-- _class: cover_c -->
<!-- _paginate: "" -->
<!-- _footer: 厚德 笃学 崇实 尚新 -->
<!-- _header: ![](../hfut-badge/HFUT_Horizontal_name&badge.svg) -->


# <!-- fit -->HFUT Awesome Marp：解决各种答辩、汇报ppt

###### 使用markdown简单快速制作ppt

汇报人：xxx
计算机23-0班
<2023xxxxxx@mail.hfut.edu.cn>

---

<!-- _class: cover_d -->
<!-- _paginate: "" -->
<!-- _footer: "厚德 笃学 崇实 尚新" -->

# <!-- fit -->HFUT Awesome Marp：解决各种答辩、汇报ppt

###### 使用markdown简单快速制作ppt

汇报人：xxx
计算机23-0班
<2023xxxxxx@mail.hfut.edu.cn>

---

<!-- _class: cover_e -->
<!-- _paginate: "" -->
<!-- _footer: ![](../hfut-badge/HFUT_Horizontal_name&badge_white.png) -->
<!-- _header: ![](../hfut-badge/HFUT_badge_white.png) -->


# <!-- fit -->Awesome Marp：轻松取代 LaTeX Beamer！

###### 使用markdown简单快速制作ppt

汇报人：xxx
计算机23-0班
<2023xxxxxx@mail.hfut.edu.cn>

---
<!-- _class: toc_a -->
<!-- _header: "CONTENTS" -->
<!-- _footer: "" -->
<!-- _paginate: "" -->

- [两栏五五分（cols-2）](#1)
- [两栏六四分（cols-2-64）](#2)
- [两栏七三分（cols-2-73）](#3)
- [三栏分栏（cols-3）](#4)
- [两行分栏（rows-2）](#5)
- [品字型分栏（pin-3）](#6)

---

<!-- _header: 目录<br>CONTENTS<br>![](../hfut-badge/HFUT_badge_white.png)-->
<!-- _class: toc_b -->
<!-- _footer: "" -->
<!-- _paginate: "" -->

- [两栏五五分（cols-2）](#1)
- [两栏六四分（cols-2-64）](#2)
- [两栏七三分（cols-2-73）](#3)
- [三栏分栏（cols-3）](#4)
- [两行分栏（rows-2）](#5)
- [品字型分栏（pin-3）](#6)


## 1. 两栏五五分（cols-2）

<!-- _class: cols-2 -->

<div class=ldiv>

**左栏内容**

使用 `<!-- _class: cols-2 -->`

支持所有 Markdown 语法：
- 列表项
- **粗体**、*斜体*
- `代码`

</div>

<div class=rdiv>

**右栏内容**

```python
def hello():
    print("Hello Marp!")
```

</div>

## 2. 两栏六四分（cols-2-64）

<!-- _class: cols-2-64 -->

<div class=ldiv>

**主要内容区（60%）**

使用 `<!-- _class: cols-2-64 -->`

- 适合放置主要内容
- 文字较多的说明
- 详细的列表项

</div>

<div class=rdiv>

**次要内容区（40%）**

![#c h:450 ](img/13.jpg)

</div>

## 3. 两栏七三分（cols-2-73）

<!-- _class: cols-2-73 -->

<div class=ldiv>

**主栏（70%）**

使用 `<!-- _class: cols-2-73 -->`

这种布局适合主要内容占据大部分空间的情况。
![ ](img/3.jpg)

</div>

<div class=rdiv>

**侧栏（30%）**

简短补充

</div>


## 4. 三栏分栏（cols-3）

<!-- _class: cols-3 -->

<div class=limg>

![ ](img/12.jpg)

</div>

<div class=mdiv>

**第二栏**

**合肥工业大学**简称**合工大**，位于安徽省**合肥市和宣城市**，创建于1945年秋，1960年10月22日被中共中央批准为全国重点大学，是教育部直属高校，“**211工程”、“985工程优势学科创新平台**”重点建设高校，“世界一流大学和一流学科建设”高校。

</div>

<div class=rimg>

![#c](img/9.jpg)

</div>

## 5. 两行分栏（rows-2）

<!-- _class: rows-2 -->

<div class="tdiv">

**上半部分**

使用 `<!-- _class: rows-2 -->`

这是上半部分的内容

</div>

<div class="bdiv">

**下半部分**

![h:200 ](img/2.jpg)

</div>

## 6. 品字型分栏（pin-3）

<!-- _class: pin-3 -->

<div class="timg">


使用 `<!-- _class: pin-3 -->`，这是顶部横向区域的内容
使用`<div class="timg">`来居中图片或文字

</div>

<div class="limg">

![h:290 ](img/1.jpg)

</div>

<div class="rdiv">

**右下内容**

右下角区域

</div>

## 7. 有序列表 + 方形序号 + 两列（cols2_ol_sq）

<!-- _class: cols2_ol_sq fglass-->

- 第一项内容
- 第二项内容
- 第三项内容
- 第四项内容
- 第五项内容
- 第六项内容
- 第七项内容
- 第八项内容

## 8. 有序列表 + 圆形序号 + 两列（cols2_ol_ci）

<!-- _class: cols2_ol_ci fglass-->

- 项目一
- 项目二
- 项目三
- 项目四
- 项目五
- 项目六
- 项目七
- 项目八

## 9. 无序列表 + 方形序号 + 两列（cols2_ul_sq）

<!-- _class: cols2_ul_sq fglass-->

- 要点 A
- 要点 B
- 要点 C
- 要点 D
- 要点 E
- 要点 F
- 要点 G
- 要点 H

## 10. 无序列表 + 圆形序号 + 两列（cols2_ul_ci）

<!-- _class: cols2_ul_ci fglass-->

- 内容 A
- 内容 B
- 内容 C
- 内容 D
- 内容 E
- 内容 F
- 内容 G
- 内容 H

## 11. 单列有序列表 + 方形序号（col1_ol_sq）

<!-- _class: col1_ol_sq fglass-->

- 步骤一：准备环境
- 步骤二：安装依赖
- 步骤三：配置参数
- 步骤四：运行测试
- 步骤五：部署上线

## 12. 单列有序列表 + 圆形序号（col1_ol_ci）

<!-- _class: col1_ol_ci fglass-->

- 阶段一：需求分析
- 阶段二：系统设计
- 阶段三：编码实现
- 阶段四：测试验证
- 阶段五：上线运维

## 13. 普通引用

> 这是一个普通的引用块，使用标准 Markdown `>` 语法。
> 
> 可以包含多段文字内容。

## 14. 紫色 Callout（bq-purple）

<!-- _class: bq-purple -->

> **紫色提示框**
> 
> 使用 `<!-- _class: bq-purple -->` 创建紫色背景的引用框，适合重要提示。
> 使用 `<!-- _class: bq-black -->` 创建黑色背景的引用框，适合严肃内容。
> 使用 `<!-- _class: bq-blue -->` 创建蓝色背景的引用框，适合信息说明。
> 使用 `<!-- _class: bq-green -->` 创建绿色背景的引用框，适合成功提示。
> 使用 `<!-- _class: bq-red -->` 创建红色背景的引用框，适合警告提示。



## 15. 行内行间公式

行内公式示例：质能方程 $E = mc^2$，勾股定理 $a^2 + b^2 = c^2$


**二次方程求根公式：**

$$x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}$$

**正态分布概率密度函数：**

$$f(x) = \frac{1}{\sigma\sqrt{2\pi}} e^{-\frac{(x-\mu)^2}{2\sigma^2}}$$



## 16. 导航栏（navbar）

<!-- _class: navbar -->
<!-- _header: \ ***@Awesome Marp*** *分栏* *列表* *引用* *公式* **导航栏** *样式*-->

**导航栏使用说明：**

- 使用 `<!-- _class: navbar -->`
- 在 `_header` 中设置：`\ ***左侧*** *其他* **当前** *页面*`
- 左侧粗斜体 `***...***`，当前页粗体 `**...**`，其他页斜体 `*...*`

## 17. 固定标题样式 A（fixedtitleA）

<!-- _class: fixedtitleA -->

<div class="div">

- 使用 `<!-- _class: fixedtitleA -->`
- 标题固定在顶部，内容从上开始排列，不再垂直居中
![h:400](img/4.jpg)

</div>

## 18. 固定标题样式 B

<!-- _class: fixedtitleB -->

<div class="div">

- 使用 `<!-- _class: fixedtitleB -->`
- 标题带有底色背景，字号略小
- 内容需包裹在 `<div class="div"></div>` 中

![#c h:350](img/5.jpg)

</div>


## 19. 微小字体（tinytext）

<!-- _class: tinytext -->

使用 `<!-- _class: tinytext -->`，字体大小为默认的 0.8 倍。这种字体适合放置大量文字内容，或者需要在一页中展示更多信息的情况。适合详细的技术文档或密集的数据展示。
使用 `<!-- _class: smalltext -->`，字体大小为默认的 0.9 倍。适合需要稍微缩小字体的场景，在保持可读性的同时容纳更多内容。
使用 `<!-- _class: largetext -->`，字体大小为默认的 1.15 倍。适合需要强调的内容或演讲场景。
使用 `<!-- _class: hugetext -->`，字体大小为默认的 1.3 倍。






## 20. 图表标题（caption）

<!-- _class: caption -->

使用 `<div class="caption">标题文字</div>` 为图表添加标题。

![#c h:350](img/1.png)

<div class="caption">
Figure 1: Elden Ring
</div>

## 21. 脚注样式（footnote）

<!-- _class: footnote -->

<div class="tdiv">

**正文内容区域**

这是正文内容，可以在这里引用脚注$^1$和$^2$。合肥工业大学$^1$是一所位于安徽的高校。

**使用方法：**
- 设置 `<!-- _class: footnote -->`
- 正文放在 `<div class="tdiv"></div>` 中
- 脚注放在 `<div class="bdiv"></div>` 中

</div>

<div class="bdiv">

1. 合肥工业大学是一所教育部直属的全国重点大学，是国家“211工程”重点建设高校。
2. 这是第二个脚注的内容说明

</div>

## 22. Python 代码

```python
def fibonacci(n):
    """计算斐波那契数列"""
    if n <= 1:
        return n
    return fibonacci(n-1) + fibonacci(n-2)

# 调用函数
result = fibonacci(10)
print(f"第10个斐波那契数是: {result}")
```


## 23. 基础表格


| 项目 | 数量 | 单价 | 总价 |
|------|------|------|------|
| 苹果 | 10 | 5.0 | 50.0 |
| 香蕉 | 8 | 3.5 | 28.0 |
| 橙子 | 12 | 4.0 | 48.0 |


## 24. YAML 配置

```yaml
---
marp: true              # 启用 Marp
size: 16:9              # 页面比例：16:9 或 4:3
theme: am_purple        # 主题名称
paginate: true          # 显示页码
headingDivider: 2       # 按二级标题分页
footer: 页脚内容        # 全局页脚
---
```

## 25. 局部指令

**常用局部指令：**

- `<!-- _class: 样式名 -->` 应用自定义样式
- `<!-- _header: "内容" -->` 设置当前页页眉
- `<!-- _footer: "内容" -->` 设置当前页页脚
- `<!-- _paginate: "" -->` 隐藏当前页页码

## 26. 图片语法

```markdown
![](image.png)              # 普通图片
![w:500](image.png)         # 指定宽度 500px
![h:300](image.png)         # 指定高度 300px
![#c](image.png)            # 居中显示
![#c w:400 h:300](img.png)  # 组合使用
```

## 27. 超链接

**外部链接：**
- [Marp 官方网站](https://marp.app/)
- [Marpit 文档](https://marpit.marp.app/)
- [VS Code Marp 插件](https://marketplace.visualstudio.com/items?itemName=marp-team.marp-vscode)

## 28. 页面跳转

**内部页面跳转：**

- 跳转到[第1页：两栏五五分](#1.-两栏五五分（cols-2）)
- 跳转到[第15页：行内公式](#15.-行内公式)
- 跳转到[第16页：导航栏](#16.-导航栏（navbar）)

---

<!-- _class: lastpage  -->
<!-- _footer: ""  -->
![ ](../hfut-badge/HFUT_Horizontal_name&badge.svg)
###### 感谢观看！ 
