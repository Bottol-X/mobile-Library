# Web 端字体系统规范
> 基于移动端设计系统适配，参考 Ant Design / Material Design / Figma / Stripe

**生成日期：** 2026-03-27  
**适用场景：** Web 应用、管理后台、SaaS 平台、营销页面

---

## 📐 设计原则

### 从移动端到 Web 端的适配策略

| 维度 | 移动端 | Web 端 | 原因 |
|------|--------|--------|------|
| **基础字号** | 16px | 14-16px | Web 端阅读距离更远，需要平衡性 |
| **行高比例** | 1.2-1.5 | 1.5-1.8 | Web 端需要更好的可读性 |
| **层级数量** | 9 级 | 11-13 级 | Web 端需要更多语义层级 |
| **最大字号** | 48px | 56-72px | Web 端大屏需要更强视觉冲击 |
| **字重范围** | 400-700 | 400-700 | 保持一致 |

### 参考标准

- **Ant Design：** 14px base, 8-scale type system
- **Material Design 3：** Responsive type scale (Display/Headline/Title/Body/Label)
- **Apple HIG (Web)：** SF Pro with dynamic sizing
- **Figma：** 12-14px UI, flexible headings
- **Stripe：** Inter font, clear hierarchy

---

## 🎨 完整字体系统

### 字体族（Font Family）

```css
/* 推荐字体栈 */
--font-family-sans: 
  -apple-system, BlinkMacSystemFont, 
  "Segoe UI", "Roboto", "Helvetica Neue", Arial,
  "Noto Sans", sans-serif,
  "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol";

/* 可选：品牌字体（如 Inter, SF Pro） */
--font-family-brand: "Inter", var(--font-family-sans);

/* 等宽字体（代码、数字） */
--font-family-mono: 
  "SF Mono", Monaco, "Cascadia Code", 
  "Roboto Mono", Consolas, "Courier New", monospace;
```

---

## 📏 Type Scale（字体层级）

### 1. Display（超大标题）
> 用于营销页面、Landing Page、首屏标题

| Token | 字号 | 行高 | 字重 | Letter Spacing | 应用场景 |
|-------|------|------|------|---------------|---------|
| `display-2xl` | 72px | 90px (1.25) | 700 (Bold) | -0.02em | Hero 标题、首屏超大标题 |
| `display-xl` | 60px | 72px (1.2) | 700 (Bold) | -0.02em | Landing Page 主标题 |
| `display-lg` | 48px | 60px (1.25) | 600 (Semibold) | -0.01em | 营销页面一级标题 |
| `display-md` | 36px | 44px (1.22) | 600 (Semibold) | -0.01em | 特性区块大标题 |

**使用建议：**
- 仅用于营销页面、首屏
- 移动端响应式缩小 30-40%
- 可配合渐变色、动画增强视觉

---

### 2. Heading（页面标题）
> 用于页面内容区标题、模块标题

| Token | 字号 | 行高 | 字重 | 对应移动端 | 应用场景 |
|-------|------|------|------|-----------|---------|
| `heading-h1` | 32px | 40px (1.25) | 600 (Semibold) | H2 (36px) | 页面主标题 |
| `heading-h2` | 24px | 32px (1.33) | 600 (Semibold) | H3 (28px) | 页面二级标题 |
| `heading-h3` | 20px | 28px (1.4) | 600 (Semibold) | T1 (24px) | 区块标题、卡片标题 |
| `heading-h4` | 18px | 28px (1.56) | 600 (Semibold) | T2 (18px) | 小区块标题 |
| `heading-h5` | 16px | 24px (1.5) | 600 (Semibold) | T3 (16px) | 列表标题、表单标题 |
| `heading-h6` | 14px | 22px (1.57) | 600 (Semibold) | - | 辅助标题 |

**使用建议：**
- `h1-h3` 用于页面结构层级
- `h4-h6` 用于组件内部标题
- 移动端同比例缩小或复用移动端规范

---

### 3. Body（正文）
> 用于段落、描述、内容区

| Token | 字号 | 行高 | 字重 | 对应移动端 | 应用场景 |
|-------|------|------|------|-----------|---------|
| `body-xl` | 18px | 28px (1.56) | 400 (Regular) | - | 大段落、营销文案 |
| `body-lg` | 16px | 24px (1.5) | 400 (Regular) | Normal (16px) | **标准正文**（最常用） |
| `body-md` | 14px | 22px (1.57) | 400 (Regular) | - | 表单说明、列表内容 |
| `body-sm` | 13px | 20px (1.54) | 400 (Regular) | C1 (13px) | 辅助说明 |
| `body-xs` | 12px | 18px (1.5) | 400 (Regular) | - | 次要内容 |

**粗体变体（Emphasis）**

| Token | 字号 | 行高 | 字重 | 应用场景 |
|-------|------|------|------|---------|
| `body-lg-strong` | 16px | 24px | 600 (Semibold) | 强调文本 |
| `body-md-strong` | 14px | 22px | 600 (Semibold) | 列表项重点 |
| `body-sm-strong` | 13px | 20px | 600 (Semibold) | 小标签强调 |

**使用建议：**
- `body-lg` 作为标准正文（16px）
- Ant Design 风格使用 `body-md` (14px)
- 强调内容用 `*-strong` 变体

---

### 4. Label（标签）
> 用于表单标签、按钮文字、Tab 标签

| Token | 字号 | 行高 | 字重 | 对应移动端 | 应用场景 |
|-------|------|------|------|-----------|---------|
| `label-lg` | 16px | 24px (1.5) | 500 (Medium) | ButtonLarge | 大按钮、主按钮 |
| `label-md` | 14px | 20px (1.43) | 500 (Medium) | - | **标准按钮、表单标签** |
| `label-sm` | 13px | 18px (1.38) | 500 (Medium) | ButtonSmall | 小按钮、Tab 标签 |
| `label-xs` | 12px | 16px (1.33) | 500 (Medium) | - | 迷你按钮、徽章 |

**使用建议：**
- 按钮文字用 `label-*` 系列
- 表单 label 用 `label-md`
- 交互元素字重建议 500-600（更清晰）

---

### 5. Caption（辅助文字）
> 用于提示、时间戳、版权信息

| Token | 字号 | 行高 | 字重 | 对应移动端 | 应用场景 |
|-------|------|------|------|-----------|---------|
| `caption-md` | 12px | 18px (1.5) | 400 (Regular) | C3 (10px) | 提示文字、帮助信息 |
| `caption-sm` | 11px | 16px (1.45) | 400 (Regular) | - | 时间戳、版权 |
| `caption-xs` | 10px | 14px (1.4) | 400 (Regular) | C3 (10px) | 小标签、角标 |

**使用建议：**
- Web 端最小 10px（移动端可到 10px）
- 辅助色配合（text-secondary）

---

### 6. Code（代码/等宽字体）
> 用于代码块、命令行、数字展示

| Token | 字号 | 行高 | 字重 | 应用场景 |
|-------|------|------|------|---------|
| `code-lg` | 16px | 24px (1.5) | 400 | 代码编辑器 |
| `code-md` | 14px | 22px (1.57) | 400 | **标准代码块** |
| `code-sm` | 13px | 20px (1.54) | 400 | 行内代码 |
| `code-xs` | 12px | 18px (1.5) | 400 | 小代码片段 |

**字体：** `font-family: var(--font-family-mono)`

---

## 🎯 语义化命名总结

### 完整 Token 清单（33 个）

#### Display（4）
- `display-2xl` / `display-xl` / `display-lg` / `display-md`

#### Heading（6）
- `heading-h1` / `heading-h2` / `heading-h3` / `heading-h4` / `heading-h5` / `heading-h6`

#### Body（8）
- `body-xl` / `body-lg` / `body-md` / `body-sm` / `body-xs`
- `body-lg-strong` / `body-md-strong` / `body-sm-strong`

#### Label（4）
- `label-lg` / `label-md` / `label-sm` / `label-xs`

#### Caption（3）
- `caption-md` / `caption-sm` / `caption-xs`

#### Code（4）
- `code-lg` / `code-md` / `code-sm` / `code-xs`

#### Utility（4）
- `font-family-sans` / `font-family-brand` / `font-family-mono`
- `line-height-base` (1.5)

---

## 💻 CSS Variables 实现

### 完整代码

```css
:root {
  /* ========== Font Family ========== */
  --font-family-sans: -apple-system, BlinkMacSystemFont, "Segoe UI", "Roboto", 
    "Helvetica Neue", Arial, "Noto Sans", sans-serif, 
    "Apple Color Emoji", "Segoe UI Emoji";
  --font-family-brand: "Inter", var(--font-family-sans);
  --font-family-mono: "SF Mono", Monaco, "Cascadia Code", 
    "Roboto Mono", Consolas, monospace;

  /* ========== Display ========== */
  --font-display-2xl: 700 72px/90px var(--font-family-sans);
  --font-display-xl: 700 60px/72px var(--font-family-sans);
  --font-display-lg: 600 48px/60px var(--font-family-sans);
  --font-display-md: 600 36px/44px var(--font-family-sans);
  
  /* Letter Spacing for Display */
  --letter-spacing-display: -0.02em;

  /* ========== Heading ========== */
  --font-heading-h1: 600 32px/40px var(--font-family-sans);
  --font-heading-h2: 600 24px/32px var(--font-family-sans);
  --font-heading-h3: 600 20px/28px var(--font-family-sans);
  --font-heading-h4: 600 18px/28px var(--font-family-sans);
  --font-heading-h5: 600 16px/24px var(--font-family-sans);
  --font-heading-h6: 600 14px/22px var(--font-family-sans);

  /* ========== Body ========== */
  --font-body-xl: 400 18px/28px var(--font-family-sans);
  --font-body-lg: 400 16px/24px var(--font-family-sans);
  --font-body-md: 400 14px/22px var(--font-family-sans);
  --font-body-sm: 400 13px/20px var(--font-family-sans);
  --font-body-xs: 400 12px/18px var(--font-family-sans);
  
  /* Body Strong (Emphasis) */
  --font-body-lg-strong: 600 16px/24px var(--font-family-sans);
  --font-body-md-strong: 600 14px/22px var(--font-family-sans);
  --font-body-sm-strong: 600 13px/20px var(--font-family-sans);

  /* ========== Label ========== */
  --font-label-lg: 500 16px/24px var(--font-family-sans);
  --font-label-md: 500 14px/20px var(--font-family-sans);
  --font-label-sm: 500 13px/18px var(--font-family-sans);
  --font-label-xs: 500 12px/16px var(--font-family-sans);

  /* ========== Caption ========== */
  --font-caption-md: 400 12px/18px var(--font-family-sans);
  --font-caption-sm: 400 11px/16px var(--font-family-sans);
  --font-caption-xs: 400 10px/14px var(--font-family-sans);

  /* ========== Code ========== */
  --font-code-lg: 400 16px/24px var(--font-family-mono);
  --font-code-md: 400 14px/22px var(--font-family-mono);
  --font-code-sm: 400 13px/20px var(--font-family-mono);
  --font-code-xs: 400 12px/18px var(--font-family-mono);

  /* ========== Utility ========== */
  --line-height-base: 1.5;
  --line-height-tight: 1.25;
  --line-height-relaxed: 1.75;
}
```

### 使用示例

```css
/* 页面主标题 */
h1 {
  font: var(--font-heading-h1);
}

/* 正文段落 */
p {
  font: var(--font-body-lg);
  color: var(--text-primary); /* 配合颜色系统 */
}

/* 强调文本 */
strong, b {
  font: var(--font-body-lg-strong);
}

/* 按钮 */
.button-primary {
  font: var(--font-label-md);
  padding: 10px 16px;
}

/* 提示文字 */
.help-text {
  font: var(--font-caption-md);
  color: var(--text-secondary);
}

/* 代码块 */
code {
  font: var(--font-code-md);
  background: var(--bg-secondary);
  padding: 2px 6px;
  border-radius: 4px;
}
```

---

## 📊 对比表：移动端 vs Web 端

| 层级 | 移动端 | Web 端 | 调整说明 |
|------|--------|--------|---------|
| **超大标题** | H1: 48px | display-lg: 48px | Web 增加更大 Display 层级 |
| **一级标题** | H2: 36px | heading-h1: 32px | Web 略小（页面内标题） |
| **二级标题** | H3: 28px | heading-h2: 24px | 保持比例缩放 |
| **正文** | Normal: 16px | body-lg: 16px | **一致** |
| **辅助文字** | C1: 13px | body-sm: 13px | **一致** |
| **按钮文字** | ButtonLarge: 16px | label-lg: 16px | **一致** |
| **最小字号** | 10px | 10px | **一致**（Web 可到 10px） |

**核心差异：**
- Web 端增加 Display 层级（72/60/48px）应对大屏
- 标题层级更细分（6 级 Heading）
- 行高更宽松（1.5-1.8）
- 正文/按钮保持与移动端一致

---

## 🎨 Figma Variables 配置

### 创建字体变量步骤

1. **打开 Figma Variables 面板**
   - 快捷键：`Ctrl/Cmd + /` → 搜索 "Variables"
   - 或：右侧属性面板 → Variables 图标

2. **创建变量集合：Typography**

```
Collection: Typography
├─ Mode 1: Default
└─ Mode 2: Compact (可选，紧凑模式)
```

3. **创建字体变量**

#### Display

| 变量名 | 值 |
|--------|-----|
| `typography/display/2xl` | 72px / 90px / Bold (700) |
| `typography/display/xl` | 60px / 72px / Bold (700) |
| `typography/display/lg` | 48px / 60px / Semibold (600) |
| `typography/display/md` | 36px / 44px / Semibold (600) |

#### Heading

| 变量名 | 值 |
|--------|-----|
| `typography/heading/h1` | 32px / 40px / Semibold (600) |
| `typography/heading/h2` | 24px / 32px / Semibold (600) |
| `typography/heading/h3` | 20px / 28px / Semibold (600) |
| `typography/heading/h4` | 18px / 28px / Semibold (600) |
| `typography/heading/h5` | 16px / 24px / Semibold (600) |
| `typography/heading/h6` | 14px / 22px / Semibold (600) |

#### Body

| 变量名 | 值 |
|--------|-----|
| `typography/body/xl` | 18px / 28px / Regular (400) |
| `typography/body/lg` | 16px / 24px / Regular (400) |
| `typography/body/md` | 14px / 22px / Regular (400) |
| `typography/body/sm` | 13px / 20px / Regular (400) |
| `typography/body/xs` | 12px / 18px / Regular (400) |

#### Label

| 变量名 | 值 |
|--------|-----|
| `typography/label/lg` | 16px / 24px / Medium (500) |
| `typography/label/md` | 14px / 20px / Medium (500) |
| `typography/label/sm` | 13px / 18px / Medium (500) |
| `typography/label/xs` | 12px / 16px / Medium (500) |

#### Caption

| 变量名 | 值 |
|--------|-----|
| `typography/caption/md` | 12px / 18px / Regular (400) |
| `typography/caption/sm` | 11px / 16px / Regular (400) |
| `typography/caption/xs` | 10px / 14px / Regular (400) |

4. **应用到组件**

```
选中文本图层 → 右侧属性面板
→ Font size: 点击 🔗 → 选择变量 typography/body/lg
→ Line height: 点击 🔗 → 选择对应行高变量
→ Font weight: 选择对应字重
```

---

## 📱 响应式策略

### 断点对应规则

| 断点 | 屏幕宽度 | Display | Heading | Body |
|------|---------|---------|---------|------|
| **Desktop** | ≥1440px | 72-48px | 32-14px | 16-12px |
| **Laptop** | 1024-1439px | 60-36px | 32-14px | 16-12px |
| **Tablet** | 768-1023px | 48-36px | 24-14px | 16-12px |
| **Mobile** | <768px | 移动端规范 | 移动端规范 | 移动端规范 |

### CSS 响应式示例

```css
/* Desktop (默认) */
h1 {
  font: var(--font-heading-h1); /* 32px */
}

/* Tablet */
@media (max-width: 1023px) {
  h1 {
    font: var(--font-heading-h2); /* 24px */
  }
}

/* Mobile */
@media (max-width: 767px) {
  h1 {
    font-size: 20px; /* 或使用移动端 T1 */
    line-height: 28px;
  }
}
```

---

## ✅ 使用检查清单

### 设计阶段

- [ ] 创建 Figma Typography Variables
- [ ] 所有文本图层绑定变量（不使用硬编码字号）
- [ ] 标题层级符合语义（h1 > h2 > h3）
- [ ] 正文至少 16px（移动端）/ 14-16px（Web）
- [ ] 辅助文字至少 12px（可读性底线）
- [ ] 行高符合规范（1.5-1.8）
- [ ] 字重符合规范（400/500/600/700）

### 开发阶段

- [ ] 导出 CSS Variables 或设计 Token JSON
- [ ] 集成到项目（Tailwind/Styled Components/CSS-in-JS）
- [ ] 组件库使用 Token 而非硬编码
- [ ] 响应式字体设置（媒体查询或 clamp）
- [ ] 字体加载优化（font-display: swap）
- [ ] 无障碍检查（最小字号、对比度）

### 协作阶段

- [ ] 设计师使用 Figma Variables
- [ ] 开发使用代码 Token
- [ ] 保持双向同步（设计变更 → 代码更新）
- [ ] 定期审查（新增组件是否符合规范）

---

## 🚀 下一步

### 立即可用

1. **复制 CSS Variables** → 粘贴到项目样式文件
2. **在 Figma 创建变量** → 按上述结构创建
3. **应用到设计稿** → 替换所有硬编码字号

### 进阶扩展

- **Tailwind Config：** 将 Token 映射到 Tailwind
- **Design Tokens JSON：** 导出标准格式（Style Dictionary）
- **Storybook 文档：** 可视化字体系统
- **暗色模式：** 调整字重（暗色下字重 +100）

---

## 📚 参考资源

- **Ant Design Typography：** https://ant.design/components/typography
- **Material Design Type Scale：** https://m3.material.io/styles/typography/type-scale-tokens
- **Apple HIG Typography：** https://developer.apple.com/design/human-interface-guidelines/typography
- **Figma Best Practices：** https://help.figma.com/hc/en-us/articles/360039957034-Create-text-styles
- **Web Typography：** https://web.dev/learn/design/typography/

---

**生成工具：** OpenClaw + ux  
**维护人：** AICO Team  
**版本：** v1.0 (2026-03-27)
