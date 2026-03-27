# Figma Variables 完全操作指南

## 🎯 目标
手把手教你在 Figma 中建立原始变量（Primitive Variables）和语义变量（Semantic Variables），并建立完整的映射关系。

---

## 📚 目录

1. [Figma Variables 基础概念](#1-figma-variables-基础概念)
2. [准备工作](#2-准备工作)
3. [创建原始变量集合](#3-创建原始变量集合)
4. [创建语义变量集合](#4-创建语义变量集合)
5. [建立映射关系](#5-建立映射关系)
6. [添加深色模式](#6-添加深色模式)
7. [应用到组件](#7-应用到组件)
8. [常见问题](#8-常见问题)

---

## 1. Figma Variables 基础概念

### 什么是 Variables？

Figma Variables（变量）是可复用的设计值，类似于编程中的变量。

**核心概念：**

```
Collection (集合)
  ├─ Mode (模式) - 例如：Light / Dark
  └─ Variables (变量)
      ├─ Variable 1
      ├─ Variable 2
      └─ Variable 3
```

### 变量类型

Figma 支持 4 种变量类型：

| 类型 | 用途 | 示例 |
|------|------|------|
| **Color** | 颜色 | `#3387FF` |
| **Number** | 数字 | `16` (间距、透明度) |
| **String** | 文本 | `SF Pro` (字体名) |
| **Boolean** | 布尔值 | `true/false` (显示/隐藏) |

### 原始变量 vs. 语义变量

```
原始变量 (Primitive)
├─ 定义基础值
├─ 例如：color/brand/primary/500 = #3387FF
└─ 不直接在设计中使用

        ↓ 映射

语义变量 (Semantic)
├─ 引用原始变量
├─ 例如：color/interactive/default → {color/brand/primary/500}
└─ 在设计中直接使用
```

**为什么这样设计？**

✅ **灵活性：** 改变原始变量，所有引用自动更新  
✅ **主题化：** 轻松切换深浅模式  
✅ **语义清晰：** 设计师知道什么场景用什么变量  
✅ **可维护：** 集中管理基础色板

---

## 2. 准备工作

### 步骤 1: 打开 Variables 面板

**方法 A：菜单**
```
顶部菜单 → View → Variables (或按 Option/Alt + Command/Ctrl + K)
```

**方法 B：右侧面板**
```
右侧设计面板 → Design → Variables 图标
```

你会看到 Variables 面板：

```
┌─────────────────────────────────────┐
│ Variables                        + │
│                                     │
│ (空白状态)                          │
│                                     │
│ Create a variable collection       │
└─────────────────────────────────────┘
```

### 步骤 2: 理解面板布局

```
┌─────────────────────────────────────┐
│ Collections (左侧)                  │
│ ├─ Collection 1                     │
│ └─ Collection 2                     │
├─────────────────────────────────────┤
│ Variables (右侧)                    │
│ ├─ Variable 1                       │
│ ├─ Variable 2                       │
│ └─ Variable 3                       │
└─────────────────────────────────────┘
```

---

## 3. 创建原始变量集合

### 🎨 第一步：创建颜色原始集合

#### 3.1 创建 Collection

1. 点击 Variables 面板右上角的 **"+"** 按钮
2. 选择 **"Create collection"**
3. 命名：`Primitives/Color`

```
Collection 命名建议：
✅ Primitives/Color
✅ Primitives/Spacing
✅ Primitives/Typography
❌ Colors (太简单)
❌ 颜色原始值 (避免中文，不利于导出)
```

#### 3.2 创建品牌色变量

**创建第一个变量：**

1. 在 `Primitives/Color` Collection 中点击 **"+"**
2. 选择变量类型：**Color**
3. 命名：`brand/primary/500`
4. 设置值：`#3387FF`

**命名格式：**
```
category/subcategory/scale

示例：
brand/primary/500
brand/primary/600
neutral/100
neutral/200
```

**批量创建品牌色：**

按照以下结构创建变量：

```
Primitives/Color
├─ brand/primary/100    #E6F0FF
├─ brand/primary/200    #CCE1FF
├─ brand/primary/300    #99C3FF
├─ brand/primary/400    #66A5FF
├─ brand/primary/500    #3387FF    ← 主品牌色
├─ brand/primary/600    #0066FF
├─ brand/primary/700    #0052CC
├─ brand/primary/800    #003D99
├─ brand/primary/900    #002966
│
├─ brand/secondary/500  #10B981
│
├─ neutral/0            #FFFFFF
├─ neutral/50           #FAFAFA
├─ neutral/100          #F5F5F5
├─ neutral/200          #E5E5E5
├─ neutral/300          #D4D4D4
├─ neutral/400          #A3A3A3
├─ neutral/500          #737373
├─ neutral/600          #525252
├─ neutral/700          #404040
├─ neutral/800          #262626
├─ neutral/900          #171717
├─ neutral/1000         #0F1721
│
├─ semantic/success/500 #10B981
├─ semantic/warning/500 #F59E0B
├─ semantic/error/500   #EF4444
└─ semantic/info/500    #3B82F6
```

**快速创建技巧：**

1. 创建第一个变量
2. 复制粘贴（Cmd/Ctrl + D）
3. 修改名称和值
4. 使用 `/` 分组会自动创建层级

**实际操作截图示意：**

```
Variables 面板示例：

┌─────────────────────────────────────┐
│ Collections                         │
│ ► Primitives/Color                  │
│                                     │
├─────────────────────────────────────┤
│ Variables                         + │
│ ▼ brand                             │
│   ▼ primary                         │
│     ⬤ 100    #E6F0FF               │
│     ⬤ 200    #CCE1FF               │
│     ⬤ 300    #99C3FF               │
│     ⬤ 400    #66A5FF               │
│     ⬤ 500    #3387FF               │
│     ⬤ 600    #0066FF               │
│     ...                             │
│ ▼ neutral                           │
│     ⬤ 0      #FFFFFF               │
│     ⬤ 50     #FAFAFA               │
│     ...                             │
└─────────────────────────────────────┘
```

#### 3.3 为变量添加描述

1. 点击变量名称右侧的 **"..."** (更多选项)
2. 选择 **"Edit variable"**
3. 在 **Description** 字段添加说明

**描述示例：**

```
brand/primary/500
Description: 主品牌色，用于主要交互元素

neutral/900
Description: 最深中性色，用于深色模式背景

semantic/success/500
Description: 成功状态色
```

---

### 📏 第二步：创建间距原始集合

#### 3.4 创建 Spacing Collection

1. 创建新 Collection：`Primitives/Spacing`
2. 变量类型选择：**Number**
3. 创建变量（4px 网格系统）：

```
Primitives/Spacing
├─ 0     0
├─ 1     4
├─ 2     8
├─ 3     12
├─ 4     16
├─ 5     20
├─ 6     24
├─ 7     28
├─ 8     32
├─ 9     36
├─ 10    40
├─ 12    48
├─ 14    56
├─ 16    64
├─ 20    80
└─ 24    96
```

**重要：** 数字变量不需要单位，Figma 会自动处理为 px

---

### 🔤 第三步：创建字体原始集合

#### 3.5 创建 Typography 相关 Collections

**字体大小：**

```
Collection: Primitives/FontSize
Type: Number

Variables:
├─ 10    10
├─ 11    11
├─ 12    12
├─ 14    14
├─ 16    16
├─ 18    18
├─ 20    20
├─ 24    24
├─ 28    28
├─ 32    32
├─ 40    40
└─ 48    48
```

**字重：**

```
Collection: Primitives/FontWeight
Type: Number

Variables:
├─ light      300
├─ regular    400
├─ medium     500
├─ semibold   600
└─ bold       700
```

**行高：**

```
Collection: Primitives/LineHeight
Type: Number

Variables:
├─ 120    1.2
├─ 140    1.4
├─ 150    1.5
├─ 160    1.6
└─ 175    1.75
```

---

### 🔲 第四步：创建圆角原始集合

```
Collection: Primitives/Radius
Type: Number

Variables:
├─ none    0
├─ xs      2
├─ sm      4
├─ base    6
├─ md      8
├─ lg      12
├─ xl      16
├─ 2xl     20
├─ 3xl     24
└─ full    9999
```

---

## 4. 创建语义变量集合

语义变量是**引用原始变量**的变量，用于描述用途而非外观。

### 🎨 第一步：创建颜色语义集合

#### 4.1 创建 Semantic/Color Collection

1. 创建新 Collection：`Semantic/Color`
2. 变量类型：**Color**
3. **创建第一个 Mode：** `Light` (默认)

#### 4.2 创建文本颜色变量并映射

**创建 text/primary 变量：**

1. 点击 **"+"** 创建变量
2. 命名：`text/primary`
3. 点击颜色值区域
4. 在颜色选择器底部，点击 **"Variables"** 图标（四个点）
5. 选择 **"Primitives/Color"** → **"neutral/1000"**
6. 设置不透明度：90%

**关键步骤截图示意：**

```
设置变量值：

┌─────────────────────────────────────┐
│ text/primary                        │
│                                     │
│ Value (Light mode)                  │
│ ┌─────────────────────────────────┐ │
│ │ [Color Picker]                  │ │
│ │                                 │ │
│ │ 🔗 Link to variable              │ │ ← 点这里
│ └─────────────────────────────────┘ │
│                                     │
│ Opacity: 90%                        │ ← 设置不透明度
└─────────────────────────────────────┘

选择变量：

┌─────────────────────────────────────┐
│ Select variable                     │
│                                     │
│ Search...                           │
│                                     │
│ ► Primitives/Color                  │
│   ► neutral                         │
│     ○ 0      #FFFFFF               │
│     ○ 50     #FAFAFA               │
│     ...                             │
│     ● 1000   #0F1721  ← 选择这个    │
└─────────────────────────────────────┘
```

**完整创建文本颜色语义变量：**

```
Semantic/Color (Light mode)
├─ text/primary       → {neutral/1000} 90%
├─ text/secondary     → {neutral/1000} 60%
├─ text/tertiary      → {neutral/1000} 45%
├─ text/disabled      → {neutral/1000} 30%
├─ text/inverse       → {neutral/0} 100%
├─ text/link          → {brand/primary/500}
├─ text/success       → {semantic/success/500}
├─ text/warning       → {semantic/warning/500}
└─ text/error         → {semantic/error/500}
```

**映射语法：**
```
{collection-name/variable-path}
```

#### 4.3 创建背景颜色语义变量

```
Semantic/Color (Light mode)
├─ background/primary     → {neutral/0}
├─ background/secondary   → {neutral/50}
├─ background/tertiary    → {neutral/100}
├─ background/elevated    → {neutral/0}
├─ background/overlay     → {neutral/1000} 50%
└─ background/inverse     → {neutral/900}
```

#### 4.4 创建边框颜色语义变量

```
Semantic/Color (Light mode)
├─ border/default         → {neutral/200}
├─ border/strong          → {neutral/300}
├─ border/subtle          → {neutral/100}
├─ border/interactive     → {brand/primary/500}
├─ border/focus           → {brand/primary/500}
└─ border/error           → {semantic/error/500}
```

#### 4.5 创建交互颜色语义变量

```
Semantic/Color (Light mode)
├─ interactive/default    → {brand/primary/500}
├─ interactive/hovered    → {brand/primary/600}
├─ interactive/pressed    → {brand/primary/700}
└─ interactive/disabled   → {neutral/300}
```

#### 4.6 创建表面颜色语义变量

```
Semantic/Color (Light mode)
├─ surface/default        → transparent (直接输入颜色值)
├─ surface/hovered        → {neutral/1000} 4%
├─ surface/pressed        → {neutral/1000} 8%
├─ surface/selected       → {brand/primary/500} 10%
└─ surface/disabled       → {neutral/1000} 2%
```

---

### 📏 第二步：创建间距语义集合

```
Collection: Semantic/Spacing
Type: Number

Variables:
├─ component/xs    → {Primitives/Spacing/1}    (4px)
├─ component/sm    → {Primitives/Spacing/2}    (8px)
├─ component/md    → {Primitives/Spacing/3}    (12px)
├─ component/lg    → {Primitives/Spacing/4}    (16px)
├─ component/xl    → {Primitives/Spacing/5}    (20px)
│
├─ layout/xs       → {Primitives/Spacing/3}    (12px)
├─ layout/sm       → {Primitives/Spacing/4}    (16px)
├─ layout/md       → {Primitives/Spacing/6}    (24px)
├─ layout/lg       → {Primitives/Spacing/8}    (32px)
├─ layout/xl       → {Primitives/Spacing/12}   (48px)
│
├─ section/sm      → {Primitives/Spacing/6}    (24px)
├─ section/md      → {Primitives/Spacing/8}    (32px)
├─ section/lg      → {Primitives/Spacing/12}   (48px)
└─ section/xl      → {Primitives/Spacing/16}   (64px)
```

**如何映射数字变量：**

1. 创建变量：`component/xs`
2. 点击值输入框右侧的 **变量图标**
3. 选择 `Primitives/Spacing/1`

---

### 🔲 第三步：创建圆角语义集合

```
Collection: Semantic/Radius
Type: Number

Variables:
├─ component/button    → {Primitives/Radius/md}     (8)
├─ component/card      → {Primitives/Radius/lg}     (12)
├─ component/modal     → {Primitives/Radius/xl}     (16)
├─ component/tag       → {Primitives/Radius/sm}     (4)
├─ component/input     → {Primitives/Radius/md}     (8)
└─ component/avatar    → {Primitives/Radius/full}   (9999)
```

---

## 5. 建立映射关系

### 映射的本质

```
原始变量（具体值） → 语义变量（用途） → 组件应用

brand/primary/500   → interactive/default → Button background
     #3387FF              (引用)              (使用)
```

### 如何检查映射关系

1. 选中语义变量
2. 查看右侧 "Value" 区域
3. 如果显示 `{variable-name}`，说明已映射
4. 如果显示具体值（如 `#3387FF`），说明是硬编码

**正确映射示例：**

```
✅ text/primary
   Value: {neutral/1000} • 90%
   
✅ interactive/default
   Value: {brand/primary/500}
```

**错误示例：**

```
❌ text/primary
   Value: #0F1721 • 90%
   (应该映射到 neutral/1000)
```

### 批量检查映射

在 Variables 面板中：

1. 选择 `Semantic/Color` Collection
2. 查看每个变量的值
3. 应该都显示 `{...}` 格式的引用

---

## 6. 添加深色模式

### 什么是 Modes？

Modes（模式）允许同一个变量在不同场景下有不同的值。

**典型用例：**
- Light / Dark 模式
- Desktop / Mobile 适配
- Brand A / Brand B 主题

### 创建 Dark Mode

#### 步骤 1: 添加 Mode

1. 选择 `Semantic/Color` Collection
2. 点击右上角的 **"..."** (更多选项)
3. 选择 **"Edit collection"**
4. 在 "Modes" 区域点击 **"+"**
5. 命名新 Mode：`Dark`
6. 点击 **"Done"**

**现在你有了两个 Mode：**

```
Semantic/Color
├─ Mode: Light (默认)
└─ Mode: Dark (新建)
```

#### 步骤 2: 设置 Dark Mode 值

**切换到 Dark Mode：**

1. 在 Variables 面板顶部，点击 Mode 下拉菜单
2. 选择 **"Dark"**

**重新映射颜色：**

```
Semantic/Color (Dark mode)

文本颜色：
├─ text/primary       → {neutral/0} 90%     (Light 模式是 neutral/1000)
├─ text/secondary     → {neutral/0} 60%
├─ text/tertiary      → {neutral/0} 45%
├─ text/disabled      → {neutral/0} 30%
├─ text/inverse       → {neutral/900}       (Light 模式是 neutral/0)
└─ text/link          → {brand/primary/400} (稍浅一点)

背景颜色：
├─ background/primary     → {neutral/900}   (Light 是 neutral/0)
├─ background/secondary   → {neutral/800}   (Light 是 neutral/50)
├─ background/tertiary    → {neutral/700}   (Light 是 neutral/100)
├─ background/elevated    → {neutral/800}
└─ background/inverse     → {neutral/0}

边框颜色：
├─ border/default         → {neutral/700}   (Light 是 neutral/200)
├─ border/strong          → {neutral/600}
└─ ...

交互颜色：
├─ interactive/default    → {brand/primary/400} (深色模式稍浅)
├─ interactive/hovered    → {brand/primary/300}
└─ ...
```

**关键规则：**

- 深色模式使用**浅色文本**（neutral/0 系列）
- 深色模式使用**深色背景**（neutral/900, 800, 700）
- 品牌色在深色模式下通常**降低一级**（500 → 400）

#### 步骤 3: 可视化对比

创建一个测试 Frame 验证：

```
Frame: Mode Test
├─ Frame: Light Mode (应用 Light mode)
│  └─ [组件实例]
└─ Frame: Dark Mode (应用 Dark mode)
   └─ [组件实例]
```

**如何切换 Frame 的 Mode：**

1. 选中 Frame
2. 右侧面板 → Layer → Variables
3. 选择对应的 Mode

---

## 7. 应用到组件

### 如何在组件中使用变量

#### 7.1 应用颜色变量

**示例：创建一个按钮**

1. 创建一个 Rectangle
2. 选中后，在右侧面板找到 **Fill**
3. 点击颜色块
4. 在颜色选择器中点击 **🔗 Variables** 图标
5. 选择 `Semantic/Color` → `interactive/default`

**变量应用指示：**

```
Fill 面板显示：

┌─────────────────────────────────────┐
│ Fill                                │
│ ⬤ {interactive/default}  ↗️        │ ← 已应用变量
└─────────────────────────────────────┘

而不是：

┌─────────────────────────────────────┐
│ Fill                                │
│ ⬤ #3387FF                          │ ← 硬编码
└─────────────────────────────────────┘
```

#### 7.2 应用间距变量

**Auto Layout 中使用：**

1. 选中有 Auto Layout 的 Frame
2. 在 **Horizontal padding** 输入框
3. 点击右侧变量图标
4. 选择 `Semantic/Spacing` → `component/lg`

#### 7.3 应用圆角变量

1. 选中形状或 Frame
2. 在 **Corner radius** 输入框
3. 点击变量图标
4. 选择 `Semantic/Radius` → `component/button`

### 完整按钮组件示例

```
Component: Button/Primary

Properties:
├─ Fill (background)        → {interactive/default}
├─ Text color               → {text/inverse}
├─ Padding horizontal       → {spacing/component/lg}
├─ Padding vertical         → {spacing/component/md}
├─ Corner radius            → {radius/component/button}
└─ Height                   → Fixed: 40px

Variants:
├─ State=Default            bg: {interactive/default}
├─ State=Hovered            bg: {interactive/hovered}
├─ State=Pressed            bg: {interactive/pressed}
└─ State=Disabled           bg: {interactive/disabled}
                            text: {text/disabled}
```

### 组件变体中应用不同变量

**创建变体：**

1. 创建多个按钮状态
2. 选中所有状态 → 右键 → **"Combine as variants"**
3. 添加 Property：`State` = `Default, Hovered, Pressed, Disabled`

**为每个变体设置变量：**

1. 选中 Default 变体 → Fill → `{interactive/default}`
2. 选中 Hovered 变体 → Fill → `{interactive/hovered}`
3. 选中 Pressed 变体 → Fill → `{interactive/pressed}`
4. 选中 Disabled 变体 → Fill → `{interactive/disabled}`

---

## 8. 常见问题

### Q1: 变量无法选择怎么办？

**问题：** 点击变量图标后找不到想要的变量

**解决方案：**
1. 检查变量类型是否匹配
   - Color 属性只能用 Color 变量
   - Number 属性只能用 Number 变量
2. 确保 Collection 已发布（Published）
3. 检查变量所在的 Library 是否已启用

### Q2: 如何重命名变量？

1. 选中变量
2. 点击 **"..."** → **"Rename"**
3. 修改名称

**注意：** 重命名会自动更新所有引用

### Q3: 如何删除变量？

1. 选中变量
2. 点击 **"..."** → **"Delete"**

**警告：** 删除前检查变量是否被引用：
- 点击变量
- 右侧会显示 **"Used in X layers"**
- 点击可查看使用位置

### Q4: 如何导出变量？

**使用 Figma Tokens Plugin：**

1. 安装插件：[Figma Tokens](https://www.figma.com/community/plugin/843461159747178978)
2. 打开插件
3. 点击 **"Sync"** → **"Export"**
4. 选择格式：JSON / CSS / etc.

### Q5: 如何批量更新变量值？

**方法 1: 直接在面板中编辑**
1. 在 Variables 面板中选中变量
2. 修改值
3. 所有引用自动更新

**方法 2: 使用 Plugin**
- 使用 **"Batch Edit Variables"** 插件批量修改

### Q6: 透明度如何处理？

**两种方式：**

**方式 1: 在原始变量中定义透明度**
```
neutral/1000/90    #0F1721 with 90% opacity
neutral/1000/60    #0F1721 with 60% opacity
```

**方式 2: 在语义变量中设置透明度**
```
text/primary       → {neutral/1000} • 90%
text/secondary     → {neutral/1000} • 60%
```

推荐方式 2，更灵活

### Q7: 如何复制变量到另一个文件？

**方法 1: 发布为 Library**
1. File → Publish styles and components
2. 在新文件中启用 Library
3. 变量自动可用

**方法 2: 复制粘贴组件**
1. 复制使用了变量的组件
2. 粘贴到新文件
3. Figma 会自动复制相关变量

### Q8: 变量和 Styles 的区别？

| 特性 | Variables | Styles |
|------|-----------|--------|
| **支持类型** | Color, Number, String, Boolean | Color, Text, Effect, Grid |
| **模式支持** | ✅ 支持（Light/Dark） | ❌ 不支持 |
| **可映射** | ✅ 可以引用其他变量 | ❌ 不能引用 |
| **用途** | Design Tokens 系统 | 快速复用样式 |

**建议：** 新项目使用 Variables，老项目可共存

---

## 🎯 完整操作清单

### ✅ 原始变量创建清单

- [ ] 创建 `Primitives/Color` Collection
  - [ ] 品牌色（100-900）
  - [ ] 中性色（0-1000）
  - [ ] 功能色（success, warning, error, info）
- [ ] 创建 `Primitives/Spacing` Collection（0-24）
- [ ] 创建 `Primitives/FontSize` Collection（10-48）
- [ ] 创建 `Primitives/FontWeight` Collection（300-700）
- [ ] 创建 `Primitives/LineHeight` Collection
- [ ] 创建 `Primitives/Radius` Collection（0-9999）

### ✅ 语义变量创建清单

- [ ] 创建 `Semantic/Color` Collection（Light mode）
  - [ ] 文本颜色（9 个）
  - [ ] 背景颜色（6 个）
  - [ ] 边框颜色（6 个）
  - [ ] 交互颜色（4 个）
  - [ ] 表面颜色（5 个）
  - [ ] 图标颜色（6 个）
- [ ] 创建 `Semantic/Spacing` Collection
  - [ ] 组件间距（5 个）
  - [ ] 布局间距（5 个）
  - [ ] 区块间距（4 个）
- [ ] 创建 `Semantic/Radius` Collection（6 个组件圆角）

### ✅ 深色模式清单

- [ ] 为 `Semantic/Color` 添加 Dark mode
- [ ] 重新映射所有颜色变量
- [ ] 创建测试 Frame 验证
- [ ] 测试所有组件在两种模式下的表现

### ✅ 应用清单

- [ ] 更新按钮组件使用变量
- [ ] 更新输入框组件使用变量
- [ ] 更新卡片组件使用变量
- [ ] 更新导航组件使用变量
- [ ] 验证所有组件深浅模式切换正常

---

## 📚 下一步

完成变量设置后：

1. **导出 Tokens**
   - 使用 Figma Tokens Plugin 导出 JSON
   - 参考 `/workspace/design-tokens-template.json`

2. **同步到代码**
   - 使用 Style Dictionary 转换
   - 参考实施指南 Phase 7

3. **建立工作流**
   - 设置 GitHub Actions 自动同步
   - 建立设计-开发协作流程

4. **文档化**
   - 在 Figma 中创建文档页面
   - 展示所有 Token 和使用示例

---

## 🎉 恭喜！

你已经掌握了在 Figma 中创建完整的 Design Token 变量系统！

**记住核心原则：**
1. 原始变量定义基础值
2. 语义变量引用原始变量并描述用途
3. 组件使用语义变量
4. 使用 Modes 支持多主题

这样的架构让你的设计系统既灵活又易维护！🚀
