# Web 端组件系统 - 尺寸间距规范
> 参考 Ant Design / Material Design 3 / Apple HIG / Tailwind / GitHub Primer / Stripe

**生成日期：** 2026-03-27  
**适用场景：** Web 应用、管理后台、SaaS 平台、企业级产品

---

## 🎯 设计原则

### 参考大厂标准

| 设计系统 | 基础单位 | 间距体系 | 组件高度 | 特点 |
|----------|---------|---------|---------|------|
| **Ant Design** | 8px | 4的倍数 | 32/40px | 企业级，14px 字号 |
| **Material Design 3** | 4dp | 4dp 网格 | 40/48/56dp | 触摸友好，8dp 基线 |
| **Apple HIG (Web)** | 8px | 8的倍数 | 32/44px | 简洁优雅 |
| **Tailwind** | 4px (1 unit) | 4的倍数 | 自由组合 | 高度灵活 |
| **GitHub Primer** | 8px | 8的倍数 | 32px | 开发者友好 |
| **Stripe** | 8px | 4/8的倍数 | 40px | 金融级精致 |

### 本系统采用

- **基础单位：** 4px（最小间距）
- **标准单位：** 8px（推荐间距）
- **网格系统：** 8px grid（组件对齐）
- **组件高度：** 32/40/48px（小/中/大）
- **圆角规范：** 4/8/12/16px（渐进式）

---

## 📏 Spacing 间距系统

### 完整间距 Token

| Token | 值 | 倍数 | 应用场景 | 移动端对应 |
|-------|-----|------|---------|-----------|
| `spacing-0` | 0px | 0 | 紧贴、重叠 | - |
| `spacing-2` | 2px | 0.5 | 极小间距（边框内边距） | - |
| `spacing-4` | 4px | 1 | 最小间距（图标与文字） | S4 |
| `spacing-8` | 8px | 2 | **标准间距**（最常用） ⭐ | S8 |
| `spacing-12` | 12px | 3 | 中等间距（输入框内边距） | S12 |
| `spacing-16` | 16px | 4 | **区块间距**（推荐） ⭐ | S16 |
| `spacing-20` | 20px | 5 | 大间距（列表项） | - |
| `spacing-24` | 24px | 6 | 区块分隔 | S24 |
| `spacing-32` | 32px | 8 | Section 间距 | S32 |
| `spacing-40` | 40px | 10 | 大区块间距 | - |
| `spacing-48` | 48px | 12 | 页面级间距 | - |
| `spacing-64` | 64px | 16 | 超大间距 | - |
| `spacing-80` | 80px | 20 | Hero 区块 | - |
| `spacing-96` | 96px | 24 | 页面顶部 | - |

**使用建议：**
- 元素内间距：4/8/12px
- 元素间间距：8/16/24px
- 区块间间距：24/32/48px
- 页面级间距：48/64/80/96px

---

## 🔘 Button 按钮

### 尺寸规范（3 种）

| 尺寸 | 高度 | 内边距（水平） | 字号 | 图标尺寸 | 圆角 | 最小宽度 |
|------|------|--------------|------|---------|------|---------|
| **Large** | 48px | 24px | 16px (label-lg) | 20px | 8px | 96px |
| **Medium** | 40px | 16px | 14px (label-md) | 18px | 8px | 80px |
| **Small** | 32px | 12px | 13px (label-sm) | 16px | 6px | 64px |

### 变体类型（8 种）

| 类型 | 描述 | 背景 | 边框 | 文字颜色 | 应用场景 |
|------|------|------|------|---------|---------|
| **Primary** | 主按钮 | `brand-primary` | 无 | 白色 | 主要操作、提交 |
| **Secondary** | 次按钮 | 透明 | `brand-primary` | `brand-primary` | 辅助操作、取消 |
| **Default** | 默认按钮 | 白色 | `line-border` | `text-primary` | 普通操作 |
| **Dashed** | 虚线按钮 | 透明 | 虚线边框 | `text-primary` | 添加项、上传 |
| **Text** | 文本按钮 | 透明 | 无 | `brand-primary` | 链接式操作 |
| **Link** | 链接按钮 | 透明 | 无 | `brand-primary` | 跳转、查看详情 |
| **Success** | 成功按钮 | `status-success` | 无 | 白色 | 确认成功操作 |
| **Danger** | 危险按钮 | `status-error` | 无 | 白色 | 删除、危险操作 |

### 状态（6 种）

- Default（默认）
- Hover（悬停）：背景加深 5-10%
- Active（按下）：背景加深 15-20%
- Focus（聚焦）：外描边 2px `brand-primary` + 透明度 20%
- Disabled（禁用）：透明度 40%，cursor: not-allowed
- Loading（加载中）：显示 spinner，禁用点击

### 图标位置

```
┌────────────────────────────┐
│  [icon]  S8  Button Text   │  左图标
└────────────────────────────┘

┌────────────────────────────┐
│  Button Text  S8  [icon]   │  右图标
└────────────────────────────┘

┌──────────┐
│  [icon]  │  仅图标（正方形）
└──────────┘
```

### 按钮组

```css
/* 水平按钮组 */
.button-group-horizontal {
  gap: 8px; /* 按钮间距 */
}

/* 合并按钮组（无间距） */
.button-group-merge {
  gap: 0;
  border-radius: 左8px 中0 右8px;
}
```

---

## 📝 Input 输入框

### 尺寸规范（3 种）

| 尺寸 | 高度 | 内边距 | 字号 | 图标尺寸 | 圆角 |
|------|------|--------|------|---------|------|
| **Large** | 48px | 12px 16px | 16px (body-lg) | 20px | 8px |
| **Medium** | 40px | 8px 12px | 14px (body-md) | 18px | 8px |
| **Small** | 32px | 4px 8px | 13px (body-sm) | 16px | 6px |

### 结构

```
┌──────────────────────────────────────┐
│  [prefix]  S8  输入内容  S8  [suffix]  │
│              ↑ placeholder            │
└──────────────────────────────────────┘
  ↑ 左侧图标/文字      右侧图标/操作 ↑
```

### 状态

| 状态 | 边框颜色 | 背景 | 说明 |
|------|---------|------|------|
| **Default** | `line-border` (#E2E2E8) | 白色 | 默认 |
| **Hover** | `brand-primary` | 白色 | 悬停 |
| **Focus** | `brand-primary` 2px | 白色 | 聚焦 + 外发光 |
| **Error** | `status-error` 2px | `status-errorBg` | 错误 |
| **Disabled** | `line-border` | `bg-disable` | 禁用 |
| **Success** | `status-success` | `status-successBg` | 成功验证 |

### 变体

#### 带标签（Label）
```
Username
┌────────────────────┐
│  输入内容          │
└────────────────────┘
Helper text here
```
- Label 上方间距：4px
- Helper text 下方间距：4px
- Helper text 字号：12px (caption-md)

#### 带前缀/后缀
```
┌──────────────────────────────┐
│  https://  |  输入内容  .com  │
└──────────────────────────────┘
```

#### 密码输入框
```
┌────────────────────────────┐
│  ••••••••  [👁 显示/隐藏]  │
└────────────────────────────┘
```

#### 搜索框
```
┌────────────────────────────┐
│  [🔍]  Search...  [×清除]  │
└────────────────────────────┘
```

---

## 🎛️ Select 选择器

### 尺寸规范（与 Input 一致）

| 尺寸 | 高度 | 内边距 | 字号 | 箭头图标 | 圆角 |
|------|------|--------|------|---------|------|
| **Large** | 48px | 12px 16px | 16px | 20px ▼ | 8px |
| **Medium** | 40px | 8px 12px | 14px | 18px ▼ | 8px |
| **Small** | 32px | 4px 8px | 13px | 16px ▼ | 6px |

### 下拉菜单

```css
/* 下拉面板 */
max-height: 256px; /* 最多显示 6-8 项 */
padding: 4px 0;
border-radius: 8px;
box-shadow: 0 4px 12px rgba(0,0,0,0.15);
margin-top: 4px; /* 与输入框间距 */
```

### 选项（Option）

| 尺寸 | 高度 | 内边距 | 字号 |
|------|------|--------|------|
| **Large** | 40px | 8px 16px | 16px |
| **Medium** | 36px | 8px 12px | 14px |
| **Small** | 32px | 6px 8px | 13px |

### 状态
- Default：白色背景
- Hover：`bg-secondary` (#FAFAFA)
- Selected：`brand-soft` (#E0E8FF) + 蓝色对勾
- Disabled：灰色文字 + 透明度 40%

### 多选（Multi-select）

```
┌─────────────────────────────────┐
│  [Tag 1 ×] [Tag 2 ×]  ▼        │
└─────────────────────────────────┘
```

Tag 尺寸：
- 高度：24px
- 内边距：4px 8px
- 圆角：4px
- 间距：4px

---

## 🔲 Checkbox 复选框

### 尺寸规范

| 尺寸 | 方框大小 | 边框 | 圆角 | 对勾尺寸 | 文字间距 | 字号 |
|------|---------|------|------|---------|---------|------|
| **Large** | 20px | 2px | 4px | 12px | 12px | 16px |
| **Medium** | 16px | 1.5px | 3px | 10px | 8px | 14px |
| **Small** | 14px | 1.5px | 3px | 8px | 8px | 13px |

### 状态

| 状态 | 边框颜色 | 背景 | 对勾 |
|------|---------|------|------|
| **Unchecked** | `line-border` | 白色 | 无 |
| **Checked** | `brand-primary` | `brand-primary` | 白色 ✓ |
| **Indeterminate** | `brand-primary` | `brand-primary` | 白色 − |
| **Disabled** | `line-border` | `bg-disable` | 灰色 |

### Checkbox Group

```
垂直排列：
☐ Option 1
☐ Option 2
☐ Option 3

间距：12px
```

---

## 🔘 Radio 单选框

### 尺寸规范

| 尺寸 | 圆形大小 | 边框 | 内圆大小 | 文字间距 | 字号 |
|------|---------|------|---------|---------|------|
| **Large** | 20px | 2px | 10px | 12px | 16px |
| **Medium** | 16px | 1.5px | 8px | 8px | 14px |
| **Small** | 14px | 1.5px | 6px | 8px | 13px |

### 状态

| 状态 | 边框颜色 | 背景 | 内圆 |
|------|---------|------|------|
| **Unselected** | `line-border` | 白色 | 无 |
| **Selected** | `brand-primary` | 白色 | `brand-primary` 实心圆 |
| **Disabled** | `line-border` | `bg-disable` | 灰色 |

---

## 🎨 Switch 开关

### 尺寸规范

| 尺寸 | 宽度 | 高度 | 圆钮直径 | 圆角 |
|------|------|------|---------|------|
| **Large** | 48px | 28px | 24px | 14px (圆形) |
| **Medium** | 40px | 24px | 20px | 12px |
| **Small** | 32px | 20px | 16px | 10px |

### 状态

| 状态 | 背景 | 圆钮位置 |
|------|------|---------|
| **Off** | `#D9D9D9` | 左侧（padding 2px） |
| **On** | `brand-primary` | 右侧（padding 2px） |
| **Disabled Off** | `#F5F5F5` | 左侧 |
| **Disabled On** | `brand-disable` | 右侧 |

### 动画

```css
transition: background-color 0.3s, transform 0.3s;
transform: translateX(20px); /* On 状态 */
```

---

## 🃏 Card 卡片

### 尺寸规范

| 元素 | 规范 | 说明 |
|------|------|------|
| **最小宽度** | 280px | 避免过窄 |
| **最大宽度** | 无限制 | 根据布局 |
| **内边距** | 16/24/32px | 小/中/大 |
| **圆角** | 8/12/16px | 标准/大卡片/特大 |
| **边框** | 1px solid `line-border` | 可选 |
| **阴影** | 0 1px 2px rgba(0,0,0,0.05) | 悬浮感 |

### 结构

```
┌────────────────────────────────┐
│  Header                        │  高度：48/56px
├────────────────────────────────┤
│  Content                       │  内边距：24px
│                                │
│                                │
├────────────────────────────────┤
│  Footer                        │  高度：48px
└────────────────────────────────┘
```

### 内部间距

- **Header：** padding 16px 24px
- **Content：** padding 24px
- **Footer：** padding 12px 24px
- **元素间距：** 12/16px

### 卡片变体

#### 简单卡片
```css
padding: 24px;
border-radius: 8px;
background: white;
box-shadow: 0 1px 2px rgba(0,0,0,0.05);
```

#### 带边框卡片
```css
border: 1px solid #E2E2E8;
box-shadow: none;
```

#### 悬浮卡片
```css
box-shadow: 0 4px 12px rgba(0,0,0,0.1);
transition: box-shadow 0.3s;

&:hover {
  box-shadow: 0 8px 24px rgba(0,0,0,0.15);
}
```

---

## 🏷️ Tag 标签

### 尺寸规范

| 尺寸 | 高度 | 内边距 | 字号 | 圆角 | 图标 |
|------|------|--------|------|------|------|
| **Large** | 32px | 8px 16px | 14px | 16px (圆形) | 16px |
| **Medium** | 24px | 4px 12px | 13px | 12px | 14px |
| **Small** | 20px | 2px 8px | 12px | 10px | 12px |

### 变体类型

| 类型 | 背景 | 文字颜色 | 边框 | 应用场景 |
|------|------|---------|------|---------|
| **Default** | `#F5F5F7` | `text-primary` | 无 | 普通标签 |
| **Primary** | `brand-soft` | `brand-primary` | 无 | 主要标签 |
| **Success** | `status-successBg` | `status-success` | 无 | 成功状态 |
| **Warning** | `status-warningBg` | `status-warning` | 无 | 警告状态 |
| **Error** | `status-errorBg` | `status-error` | 无 | 错误状态 |
| **Outlined** | 透明 | `text-primary` | 1px | 描边标签 |

### 可关闭标签

```
┌───────────────┐
│  Tag Name  ×  │  × 图标 14px，间距 4px
└───────────────┘
```

---

## 📑 Tabs 标签页

### 尺寸规范

#### 线条型（Line Tabs）

| 尺寸 | 高度 | 内边距 | 字号 | 下划线高度 |
|------|------|--------|------|-----------|
| **Large** | 48px | 16px 24px | 16px | 3px |
| **Medium** | 40px | 12px 16px | 14px | 2px |
| **Small** | 32px | 8px 12px | 13px | 2px |

#### 卡片型（Card Tabs）

| 尺寸 | 高度 | 内边距 | 字号 | 圆角 |
|------|------|--------|------|------|
| **Large** | 40px | 12px 24px | 16px | 8px |
| **Medium** | 36px | 10px 16px | 14px | 6px |
| **Small** | 32px | 8px 12px | 13px | 6px |

### 状态

| 状态 | 文字颜色 | 下划线/背景 |
|------|---------|------------|
| **Default** | `text-secondary` | 无 |
| **Hover** | `text-primary` | 无 |
| **Active** | `brand-primary` | `brand-primary` 下划线 |
| **Disabled** | `text-disable` | 无 |

### Tab 间距

```css
gap: 24px; /* Line Tabs */
gap: 8px;  /* Card Tabs */
```

---

## 🗂️ Table 表格

### 尺寸规范

| 元素 | 高度 | 内边距 | 字号 |
|------|------|--------|------|
| **表头（Header）** | 48px | 12px 16px | 14px (label-md) |
| **行（Row）Large** | 56px | 12px 16px | 14px |
| **行（Row）Medium** | 48px | 12px 16px | 14px |
| **行（Row）Small** | 40px | 8px 12px | 13px |

### 列宽规范

| 列类型 | 最小宽度 | 推荐宽度 | 说明 |
|--------|---------|---------|------|
| **序号** | 48px | 64px | # |
| **复选框** | 48px | 48px | ☐ |
| **图标** | 40px | 56px | 单图标 |
| **操作** | 80px | 120px | 编辑/删除 |
| **状态** | 80px | 100px | Tag 标签 |
| **时间** | 120px | 160px | 2026-03-27 09:10 |
| **短文本** | 100px | 150px | 名称 |
| **长文本** | 200px | 300px | 描述 |

### 边框和分割线

```css
/* 表头底部 */
border-bottom: 1px solid #E2E2E8;

/* 行分割线 */
border-bottom: 1px solid #F5F5F7;

/* 外边框 */
border: 1px solid #E2E2E8;
border-radius: 8px;
```

### 状态

| 状态 | 背景颜色 | 说明 |
|------|---------|------|
| **Default** | 白色 | 默认 |
| **Hover** | `#FAFAFA` | 悬停行 |
| **Selected** | `#E0E8FF` | 选中行 |
| **Stripe** | `#FAFAFA` | 斑马纹（偶数行） |

### 固定列/表头

```css
/* 固定表头 */
position: sticky;
top: 0;
z-index: 10;
background: white;

/* 固定左侧列 */
position: sticky;
left: 0;
z-index: 5;
```

---

## 🧭 Navigation 导航

### 顶部导航（Header）

| 元素 | 高度 | 内边距 | 字号 |
|------|------|--------|------|
| **Header** | 64px | 0 24px | - |
| **Logo 区域** | 64px | 16px | - |
| **菜单项** | 64px | 16px 24px | 14px |
| **用户区域** | 64px | 12px | 14px |

### 侧边导航（Sidebar）

| 元素 | 宽度 | 高度 | 内边距 | 字号 |
|------|------|------|--------|------|
| **Sidebar** | 240px / 200px | 100vh | 16px | - |
| **菜单项** | 100% | 40px | 12px 16px | 14px |
| **子菜单项** | 100% | 36px | 12px 16px 12px 32px | 13px |
| **折叠 Sidebar** | 64px | 100vh | 8px | - |

### 面包屑（Breadcrumb）

```css
/* 容器 */
height: 32px;
padding: 0;
font-size: 14px;

/* 分隔符 */
margin: 0 8px;
color: #999;
```

---

## 🔔 Badge 徽章

### 尺寸规范

| 类型 | 最小尺寸 | 高度 | 内边距 | 字号 |
|------|---------|------|--------|------|
| **圆点** | 8px | 8px | - | - |
| **数字（1位）** | 18px | 18px | - | 12px |
| **数字（2位）** | 自适应 | 18px | 0 6px | 12px |
| **文字** | 自适应 | 20px | 0 8px | 12px |

### 位置

```
┌─────────────┐
│   Content   │(●) 右上角徽章
└─────────────┘
  offset: -4px -4px
```

---

## 🖼️ Avatar 头像

### 尺寸规范

| 尺寸 | 大小 | 字号 | 圆角 | 应用场景 |
|------|------|------|------|---------|
| **XL** | 64px | 24px | 32px (圆形) / 8px | 个人主页 |
| **Large** | 48px | 18px | 24px / 6px | 用户卡片 |
| **Medium** | 40px | 16px | 20px / 6px | 列表、评论 |
| **Small** | 32px | 14px | 16px / 4px | 紧凑列表 |
| **XS** | 24px | 12px | 12px / 4px | 标签、徽章 |

### 头像组（Avatar Group）

```
重叠间距：-8px（Medium）
最大显示：5 个，其余显示 +N
```

---

## 🎯 Icon 图标

### 尺寸规范

| 场景 | 尺寸 | 应用 |
|------|------|------|
| **按钮图标（Large）** | 20px | 大按钮内 |
| **按钮图标（Medium）** | 18px | 标准按钮内 |
| **按钮图标（Small）** | 16px | 小按钮内 |
| **输入框图标** | 16-18px | 输入框前缀/后缀 |
| **菜单图标** | 18-20px | 导航菜单 |
| **列表图标** | 16px | 列表项 |
| **独立图标** | 24px | 单独展示 |
| **大图标** | 48-64px | 空状态、引导 |

### 与文字间距

```css
/* 左图标 */
margin-right: 8px;

/* 右图标 */
margin-left: 8px;

/* 独立图标 */
margin: 0;
```

---

## 🔔 Modal 模态框

### 尺寸规范

| 尺寸 | 宽度 | 高度 | 应用场景 |
|------|------|------|---------|
| **Small** | 400px | 自适应 | 确认框、简单表单 |
| **Medium** | 600px | 自适应 | 标准表单、详情 |
| **Large** | 800px | 自适应 | 复杂表单、多步骤 |
| **Fullscreen** | 100vw - 48px | 100vh - 48px | 大数据展示 |

### 结构

```
┌──────────────────────────────┐
│  Header (56px)               │
│  ───────────────────────────  │
│  Content                     │
│  padding: 24px               │
│                              │
│  ───────────────────────────  │
│  Footer (64px)               │
│  [Cancel]  [OK]              │
└──────────────────────────────┘
```

### 内边距

- Header：16px 24px
- Content：24px
- Footer：16px 24px
- 按钮间距：8px

### 遮罩

```css
background: rgba(0, 0, 0, 0.45);
backdrop-filter: blur(4px); /* 可选 */
```

---

## 🎈 Tooltip / Popover

### Tooltip

| 元素 | 规范 |
|------|------|
| **最大宽度** | 240px |
| **内边距** | 8px 12px |
| **字号** | 13px (body-sm) |
| **圆角** | 6px |
| **背景** | rgba(0,0,0,0.85) |
| **箭头大小** | 6px |

### Popover

| 元素 | 规范 |
|------|------|
| **最小宽度** | 180px |
| **最大宽度** | 360px |
| **内边距** | 12px 16px |
| **字号** | 14px (body-md) |
| **圆角** | 8px |
| **阴影** | 0 4px 16px rgba(0,0,0,0.15) |

---

## 📦 完整组件清单

### 基础组件
- ✅ Button（按钮）
- ✅ Icon（图标）
- ✅ Typography（排版）

### 输入组件
- ✅ Input（输入框）
- ✅ Select（选择器）
- ✅ Checkbox（复选框）
- ✅ Radio（单选框）
- ✅ Switch（开关）
- 🔄 Textarea（文本域）
- 🔄 DatePicker（日期选择器）
- 🔄 TimePicker（时间选择器）
- 🔄 Upload（上传）
- 🔄 Slider（滑块）
- 🔄 Rate（评分）

### 数据展示
- ✅ Table（表格）
- ✅ Tag（标签）
- ✅ Badge（徽章）
- ✅ Avatar（头像）
- ✅ Card（卡片）
- 🔄 List（列表）
- 🔄 Tree（树形控件）
- 🔄 Progress（进度条）
- 🔄 Timeline（时间轴）

### 导航
- ✅ Navigation（导航栏）
- ✅ Tabs（标签页）
- ✅ Breadcrumb（面包屑）
- 🔄 Pagination（分页）
- 🔄 Steps（步骤条）
- 🔄 Menu（菜单）

### 反馈
- ✅ Modal（模态框）
- ✅ Tooltip（文字提示）
- ✅ Popover（气泡卡片）
- 🔄 Alert（警告提示）
- 🔄 Message（全局提示）
- 🔄 Notification（通知提醒框）
- 🔄 Drawer（抽屉）
- 🔄 Skeleton（骨架屏）
- 🔄 Spin（加载中）

---

## 📊 设计系统成熟度

| 维度 | 评分 | 说明 |
|------|------|------|
| **间距系统** | ⭐⭐⭐⭐⭐ | 14 级间距，4px 基础单位 |
| **组件覆盖** | ⭐⭐⭐⭐ | 主要组件完整，部分待扩展 |
| **尺寸一致性** | ⭐⭐⭐⭐⭐ | 3 种尺寸（S/M/L）统一 |
| **大厂对标** | ⭐⭐⭐⭐⭐ | 参考 6 大设计系统 |
| **响应式支持** | ⭐⭐⭐⭐ | 详见布局系统文档 |

**总体评分：4.6 / 5.0** ⭐⭐⭐⭐

---

## 🔗 相关文档

- **布局系统：** `web-layout-system.md`
- **字体系统：** `web-typography-system.md`
- **颜色系统：** `mobile_design_system_analysis.md`（复用移动端）
- **CSS 实现：** `web-component.css`
- **演示页面：** `component-demo.html`

---

**生成日期：** 2026-03-27  
**维护人：** ux (AICO Team)  
**版本：** v1.0
