# Figma Design Tokens 实施指南

## 🎯 目标
将现有的 Mobile 组件库升级为基于 Design Tokens 的系统化设计体系

---

## 📋 实施检查清单

### Phase 1: 准备工作 ✓

- [ ] 安装 Figma Tokens Plugin 或使用原生 Variables
- [ ] 备份当前设计文件
- [ ] 创建新的 Token 测试分支
- [ ] 组建评审小组（至少包含 1 名设计师 + 1 名开发者）
- [ ] 阅读完整的命名规范文档

### Phase 2: 审计现有资源 ✓

#### 颜色审计
- [ ] 导出所有使用的颜色值
- [ ] 识别重复的颜色（允许 ±5 差异视为相同）
- [ ] 统计每个颜色的使用频率
- [ ] 创建颜色映射表

**工具：**
```
1. 使用 Figma Plugin: "Color Shades Generator"
2. 或手动创建表格记录
```

**示例输出：**
```
现有颜色分析：
#0F1721 (90% opacity) → 使用 156 次 → 映射为 color.text.primary
#0F1721 (60% opacity) → 使用 89 次  → 映射为 color.text.secondary
#FFFFFF → 使用 234 次 → 映射为 color.background.primary (light mode)
```

#### 字体审计
- [ ] 列出所有字体大小
- [ ] 列出所有字重组合
- [ ] 识别行高使用模式
- [ ] 统计字体样式的应用场景

**示例输出：**
```
现有字体大小：10, 11, 12, 14, 16, 18, 20, 24, 28, 32, 40, 48
现有字重：Light(300), Regular(400), Medium(500), Semibold(600), Bold(700)
```

#### 间距审计
- [ ] 收集所有 padding/margin 值
- [ ] 识别间距模式（4px、8px 网格系统）
- [ ] 统计使用频率
- [ ] 创建间距标准化建议

#### 圆角审计
- [ ] 收集所有 border-radius 值
- [ ] 按组件类型分类
- [ ] 创建圆角标准

### Phase 3: 创建原始 Token (Primitive Tokens) ✓

#### 3.1 颜色原始 Token

**在 Figma 中创建变量集合：**

```
Collection: Color/Primitives
Mode: Default

Variables:
├─ brand/primary/100    #E6F0FF
├─ brand/primary/200    #CCE1FF
├─ brand/primary/300    #99C3FF
├─ brand/primary/400    #66A5FF
├─ brand/primary/500    #3387FF  ← 主品牌色
├─ brand/primary/600    #0066FF
├─ brand/primary/700    #0052CC
├─ brand/primary/800    #003D99
└─ brand/primary/900    #002966

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
└─ neutral/1000         #0F1721

├─ semantic/success/500  #10B981
├─ semantic/warning/500  #F59E0B
├─ semantic/error/500    #EF4444
└─ semantic/info/500     #3B82F6
```

#### 3.2 字体原始 Token

```
Collection: Typography/Primitives

Font Size:
├─ size/10    10px
├─ size/11    11px
├─ size/12    12px
├─ size/14    14px
├─ size/16    16px
├─ size/18    18px
├─ size/20    20px
├─ size/24    24px
├─ size/28    28px
├─ size/32    32px
├─ size/40    40px
└─ size/48    48px

Font Weight:
├─ weight/light       300
├─ weight/regular     400
├─ weight/medium      500
├─ weight/semibold    600
└─ weight/bold        700

Line Height:
├─ lineHeight/120     1.2
├─ lineHeight/140     1.4
├─ lineHeight/150     1.5
├─ lineHeight/160     1.6
└─ lineHeight/175     1.75
```

#### 3.3 间距原始 Token

```
Collection: Spacing/Primitives

├─ 0      0px
├─ 1      4px
├─ 2      8px
├─ 3      12px
├─ 4      16px
├─ 5      20px
├─ 6      24px
├─ 7      28px
├─ 8      32px
├─ 9      36px
├─ 10     40px
├─ 12     48px
├─ 14     56px
├─ 16     64px
├─ 20     80px
└─ 24     96px
```

### Phase 4: 创建语义 Token (Semantic Tokens) ✓

#### 4.1 文本颜色语义 Token

```
Collection: Color/Semantic
Mode: Light (默认)

Text Colors:
├─ text/primary      → {neutral/900}    90% opacity
├─ text/secondary    → {neutral/900}    60% opacity
├─ text/tertiary     → {neutral/900}    45% opacity
├─ text/disabled     → {neutral/900}    30% opacity
├─ text/inverse      → {neutral/0}
├─ text/link         → {brand/primary/500}
├─ text/success      → {semantic/success/600}
├─ text/warning      → {semantic/warning/600}
└─ text/error        → {semantic/error/600}

Background Colors:
├─ background/primary     → {neutral/0}
├─ background/secondary   → {neutral/50}
├─ background/tertiary    → {neutral/100}
├─ background/elevated    → {neutral/0}
├─ background/overlay     → {neutral/900} 50% opacity
└─ background/inverse     → {neutral/900}

Border Colors:
├─ border/default        → {neutral/200}
├─ border/strong         → {neutral/300}
├─ border/subtle         → {neutral/100}
├─ border/interactive    → {brand/primary/500}
├─ border/focus          → {brand/primary/500}
└─ border/error          → {semantic/error/500}

Interactive Colors:
├─ interactive/default   → {brand/primary/500}
├─ interactive/hovered   → {brand/primary/600}
├─ interactive/pressed   → {brand/primary/700}
└─ interactive/disabled  → {neutral/300}
```

**添加深色模式：**

```
Mode: Dark

Text Colors:
├─ text/primary      → {neutral/0}      90% opacity
├─ text/secondary    → {neutral/0}      60% opacity
├─ text/tertiary     → {neutral/0}      45% opacity
├─ text/disabled     → {neutral/0}      30% opacity
├─ text/inverse      → {neutral/900}
...

Background Colors:
├─ background/primary     → {neutral/900}
├─ background/secondary   → {neutral/800}
├─ background/tertiary    → {neutral/700}
...
```

#### 4.2 排版语义 Token

在 Figma 中创建 Text Styles（而非变量）：

```
Text Styles:

Display:
├─ Display/Large
│   Font: SF Pro Bold 48px
│   Line: 1.2
│   Color: {color/text/primary}
│
├─ Display/Medium
│   Font: SF Pro Bold 40px
│   Line: 1.2
│   Color: {color/text/primary}
│
└─ Display/Small
    Font: SF Pro Bold 32px
    Line: 1.25
    Color: {color/text/primary}

Headline:
├─ Headline/H1
│   Font: SF Pro Bold 28px
│   Line: 1.3
│   Color: {color/text/primary}
│
├─ Headline/H2
│   Font: SF Pro Bold 24px
│   Line: 1.3
│   Color: {color/text/primary}
│
└─ Headline/H3
    Font: SF Pro Semibold 20px
    Line: 1.4
    Color: {color/text/primary}

Title:
├─ Title/T1
│   Font: SF Pro Semibold 18px
│   Line: 1.4
│   Color: {color/text/primary}
│
├─ Title/T2
│   Font: SF Pro Semibold 16px
│   Line: 1.5
│   Color: {color/text/primary}
│
└─ Title/T3
    Font: SF Pro Semibold 14px
    Line: 1.5
    Color: {color/text/primary}

Body:
├─ Body/Large
│   Font: SF Pro Regular 16px
│   Line: 1.5
│   Color: {color/text/primary}
│
├─ Body/Base
│   Font: SF Pro Regular 14px
│   Line: 1.5
│   Color: {color/text/primary}
│
├─ Body/Small
│   Font: SF Pro Regular 12px
│   Line: 1.5
│   Color: {color/text/primary}
│
├─ Body/Large Emphasis
│   Font: SF Pro Medium 16px
│   Line: 1.5
│   Color: {color/text/primary}
│
├─ Body/Base Emphasis
│   Font: SF Pro Medium 14px
│   Line: 1.5
│   Color: {color/text/primary}
│
└─ Body/Small Emphasis
    Font: SF Pro Medium 12px
    Line: 1.5
    Color: {color/text/primary}

Caption:
├─ Caption/C1
│   Font: SF Pro Regular 12px
│   Line: 1.4
│   Color: {color/text/secondary}
│
├─ Caption/C2
│   Font: SF Pro Regular 11px
│   Line: 1.4
│   Color: {color/text/secondary}
│
└─ Caption/C3
    Font: SF Pro Regular 10px
    Line: 1.4
    Color: {color/text/tertiary}

Interactive:
├─ Interactive/Button Large
│   Font: SF Pro Medium 16px
│   Line: 1.0
│   Color: varies by button type
│
├─ Interactive/Button Medium
│   Font: SF Pro Medium 14px
│   Line: 1.0
│   Color: varies by button type
│
├─ Interactive/Button Small
│   Font: SF Pro Medium 12px
│   Line: 1.0
│   Color: varies by button type
│
└─ Interactive/Link
    Font: SF Pro Regular 14px
    Line: 1.5
    Color: {color/text/link}
    Decoration: underline
```

### Phase 5: 更新组件库 ✓

#### 5.1 按钮组件迁移示例

**Before (旧方式):**
```
Button - Primary
├─ Background: #3387FF (hardcoded)
├─ Text: SF Pro Medium 14px, #FFFFFF (hardcoded)
├─ Padding: 12px 20px (hardcoded)
└─ Border Radius: 8px (hardcoded)
```

**After (新方式):**
```
Button - Primary
├─ Background: {color/interactive/default}
├─ Text: {typography/interactive/button-medium}
├─ Padding: {spacing/3} {spacing/5}
└─ Border Radius: {radius/component/button}

States:
├─ Default:   bg={color/interactive/default}
├─ Hovered:   bg={color/interactive/hovered}
├─ Pressed:   bg={color/interactive/pressed}
└─ Disabled:  bg={color/interactive/disabled}
```

**实施步骤：**
1. 选中组件的主实例
2. 在属性面板中，点击颜色填充
3. 点击变量图标（四个点）
4. 选择对应的语义变量
5. 重复上述步骤应用到所有属性
6. 为所有变体状态应用对应变量

#### 5.2 组件变量映射表

创建一个映射文档，记录每个组件使用的 token：

```markdown
## Button 组件 Token 映射

| 属性 | Default | Hovered | Pressed | Disabled |
|------|---------|---------|---------|----------|
| Background (Primary) | interactive/default | interactive/hovered | interactive/pressed | interactive/disabled |
| Text Color (Primary) | text/inverse | text/inverse | text/inverse | text/disabled |
| Border | - | - | - | - |
| Padding Horizontal | spacing/5 | spacing/5 | spacing/5 | spacing/5 |
| Padding Vertical | spacing/3 | spacing/3 | spacing/3 | spacing/3 |
| Border Radius | radius/component/button | radius/component/button | radius/component/button | radius/component/button |
| Shadow | shadow/component/button | shadow/md | - | - |
| Height (Large) | size/height/xl | - | - | - |
| Height (Medium) | size/height/lg | - | - | - |
| Height (Small) | size/height/base | - | - | - |
| Typography (Large) | typography/interactive/button-large | - | - | - |
| Typography (Medium) | typography/interactive/button-medium | - | - | - |
| Typography (Small) | typography/interactive/button-small | - | - | - |
```

### Phase 6: 文档化 ✓

#### 6.1 在 Figma 中创建文档页面

**页面结构：**
```
📄 📖 Design Tokens Documentation
├─ 🎨 Color System
│  ├─ Color Palette (原始颜色展示)
│  ├─ Semantic Colors (语义颜色应用示例)
│  ├─ Light Mode
│  └─ Dark Mode
│
├─ ✍️ Typography System
│  ├─ Type Scale (字体大小展示)
│  ├─ Font Weights
│  ├─ Text Styles (所有样式卡片)
│  └─ Usage Examples
│
├─ 📏 Spacing System
│  ├─ Spacing Scale (视觉化展示)
│  ├─ Component Spacing
│  └─ Layout Spacing
│
├─ 🔲 Other Tokens
│  ├─ Border Radius
│  ├─ Shadows
│  ├─ Sizes
│  └─ Motion
│
└─ 📚 Guidelines
   ├─ When to Use What
   ├─ Do's and Don'ts
   └─ Migration Guide
```

#### 6.2 创建可视化文档

**Color Token 展示卡片模板：**
```
┌─────────────────────────────┐
│                             │
│  ███████████████████████   │  ← 颜色样本
│                             │
│  color.text.primary         │  ← Token 名称
│  #0F1721 · 90% opacity      │  ← 具体值
│  Neutral 900                │  ← 引用的原始 token
│                             │
│  用于主要文本内容，如标题、  │  ← 使用场景
│  正文第一段等                │
│                             │
│  ✅ 列表项标题               │  ← Do
│  ✅ 文章标题                 │
│  ❌ 占位符文本               │  ← Don't
│  ❌ 禁用状态文本             │
└─────────────────────────────┘
```

**Typography Token 展示卡片模板：**
```
┌─────────────────────────────────────┐
│                                     │
│  The quick brown fox              │  ← 样本文字
│                                     │
│  typography.headline.h2             │  ← Token 名称
│  Font: SF Pro Bold                  │
│  Size: 24px (1.5rem)                │
│  Line Height: 31.2px (1.3)          │
│  Letter Spacing: -0.2px             │
│                                     │
│  用于二级标题、区块标题等            │  ← 使用场景
│                                     │
│  ✅ 文章副标题                       │
│  ✅ 卡片组标题                       │
│  ❌ 正文内容                         │
└─────────────────────────────────────┘
```

### Phase 7: 导出到开发 ✓

#### 7.1 使用 Figma Tokens Plugin 导出

**导出 JSON 格式：**
```json
{
  "color": {
    "text": {
      "primary": {
        "value": "{color.neutral.900}",
        "type": "color",
        "description": "主要文本颜色",
        "$extensions": {
          "mode": {
            "light": "{color.neutral.900}",
            "dark": "{color.neutral.0}"
          }
        }
      }
    }
  },
  "spacing": {
    "4": {
      "value": "16px",
      "type": "spacing"
    }
  },
  "typography": {
    "body": {
      "base": {
        "value": {
          "fontFamily": "{font.family.system}",
          "fontSize": "{font.size.base}",
          "fontWeight": "{font.weight.regular}",
          "lineHeight": "{font.lineHeight.normal}"
        },
        "type": "typography"
      }
    }
  }
}
```

#### 7.2 使用 Style Dictionary 转换

**安装 Style Dictionary：**
```bash
npm install -g style-dictionary
```

**创建配置文件 `config.json`：**
```json
{
  "source": ["tokens/**/*.json"],
  "platforms": {
    "css": {
      "transformGroup": "css",
      "buildPath": "build/css/",
      "files": [
        {
          "destination": "variables.css",
          "format": "css/variables"
        }
      ]
    },
    "scss": {
      "transformGroup": "scss",
      "buildPath": "build/scss/",
      "files": [
        {
          "destination": "_variables.scss",
          "format": "scss/variables"
        }
      ]
    },
    "js": {
      "transformGroup": "js",
      "buildPath": "build/js/",
      "files": [
        {
          "destination": "tokens.js",
          "format": "javascript/es6"
        }
      ]
    },
    "json": {
      "transformGroup": "js",
      "buildPath": "build/json/",
      "files": [
        {
          "destination": "tokens.json",
          "format": "json/flat"
        }
      ]
    },
    "ios": {
      "transformGroup": "ios",
      "buildPath": "build/ios/",
      "files": [
        {
          "destination": "Tokens.swift",
          "format": "ios-swift/class.swift",
          "className": "DesignTokens"
        }
      ]
    },
    "android": {
      "transformGroup": "android",
      "buildPath": "build/android/",
      "files": [
        {
          "destination": "colors.xml",
          "format": "android/colors"
        },
        {
          "destination": "dimens.xml",
          "format": "android/dimens"
        }
      ]
    }
  }
}
```

**运行转换：**
```bash
style-dictionary build
```

**输出示例 (CSS)：**
```css
:root {
  --color-text-primary: rgba(15, 23, 33, 0.9);
  --color-text-secondary: rgba(15, 23, 33, 0.6);
  --color-background-primary: #FFFFFF;
  --spacing-4: 16px;
  --radius-component-button: 8px;
  --typography-body-base-font-size: 14px;
  --typography-body-base-line-height: 1.5;
}

[data-theme="dark"] {
  --color-text-primary: rgba(255, 255, 255, 0.9);
  --color-text-secondary: rgba(255, 255, 255, 0.6);
  --color-background-primary: #0F1721;
}
```

**输出示例 (iOS Swift)：**
```swift
public class DesignTokens {
    public static let colorTextPrimary = UIColor(red: 0.059, green: 0.090, blue: 0.129, alpha: 0.9)
    public static let colorBackgroundPrimary = UIColor(red: 1.0, green: 1.0, blue: 1.0, alpha: 1.0)
    public static let spacing4: CGFloat = 16.0
    public static let radiusComponentButton: CGFloat = 8.0
}
```

**输出示例 (Android XML)：**
```xml
<?xml version="1.0" encoding="UTF-8"?>
<resources>
  <color name="color_text_primary">#E60F1721</color>
  <color name="color_background_primary">#FFFFFF</color>
  <dimen name="spacing_4">16dp</dimen>
  <dimen name="radius_component_button">8dp</dimen>
</resources>
```

### Phase 8: 建立同步流程 ✓

#### 8.1 创建 GitHub Actions 自动化

**`.github/workflows/sync-tokens.yml`：**
```yaml
name: Sync Design Tokens

on:
  push:
    branches:
      - main
    paths:
      - 'tokens/**'
  workflow_dispatch:

jobs:
  build-tokens:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v3

      - name: Setup Node.js
        uses: actions/setup-node@v3
        with:
          node-version: '18'

      - name: Install Style Dictionary
        run: npm install -g style-dictionary

      - name: Build Tokens
        run: style-dictionary build

      - name: Commit built tokens
        run: |
          git config --local user.email "action@github.com"
          git config --local user.name "GitHub Action"
          git add build/
          git diff --quiet && git diff --staged --quiet || git commit -m "chore: update built tokens"
          git push

      - name: Create PR to development
        uses: peter-evans/create-pull-request@v5
        with:
          branch: tokens-update
          title: '[Auto] Design Tokens Update'
          body: 'Automated token sync from Figma'
```

#### 8.2 版本管理策略

**语义化版本：**
```
主版本.次版本.修订号

主版本：破坏性变更（删除 token、重命名 token）
次版本：新增功能（新增 token、新增组件）
修订号：修复和微调（颜色微调、间距调整）

示例：
1.0.0 → 1.1.0  新增深色模式 token
1.1.0 → 1.1.1  调整 primary color 色值
1.1.1 → 2.0.0  重命名所有 typography token
```

**变更日志格式：**
```markdown
# Changelog

## [2.0.0] - 2026-04-15

### 💥 Breaking Changes
- 重命名所有 typography token，从 `text-*` 改为 `typography.*`
- 移除 `color.gray.*`，统一使用 `color.neutral.*`

### ✨ Added
- 新增深色模式支持
- 新增 `shadow.component.*` 语义阴影
- 新增 `motion.*` 动画 token

### 🔧 Changed
- 调整 `color.brand.primary.500` 从 #3387FF 到 #0066FF
- 统一 spacing scale，移除不规则值

### 🗑️ Deprecated
- `color.gray.*` 已废弃，请使用 `color.neutral.*`
- `font-size-*` 已废弃，请使用 `typography.*`

### 🔥 Removed
- 移除所有 `old-*` 前缀的旧 token

## [1.2.0] - 2026-03-25

### ✨ Added
- 新增 `radius.component.*` 语义圆角

### 🔧 Changed
- 微调 `spacing.component.*` 值以更好对齐 8px 网格
```

---

## 🛠️ 工具和插件推荐

### Figma 插件

1. **Figma Tokens (Tokens Studio)**
   - 功能：Token 管理、导出、同步
   - 免费/付费：免费基础版 + 付费 Pro 版
   - 推荐度：⭐⭐⭐⭐⭐

2. **Color Shades Generator**
   - 功能：自动生成颜色色阶
   - 推荐度：⭐⭐⭐⭐

3. **Contrast**
   - 功能：检查颜色对比度
   - 推荐度：⭐⭐⭐⭐⭐

4. **Stark**
   - 功能：无障碍设计检查
   - 推荐度：⭐⭐⭐⭐

5. **Autoflow**
   - 功能：自动绘制间距标注
   - 推荐度：⭐⭐⭐

### 代码工具

1. **Style Dictionary**
   - 功能：Token 格式转换
   - 支持：CSS, SCSS, JS, iOS, Android, Flutter
   - 推荐度：⭐⭐⭐⭐⭐

2. **Theo (Salesforce)**
   - 功能：Design Token 转换工具
   - 推荐度：⭐⭐⭐⭐

3. **Diez**
   - 功能：跨平台设计 token 工具链
   - 推荐度：⭐⭐⭐

---

## 🚨 常见陷阱和注意事项

### ❌ 陷阱 1：过度抽象

**错误示例：**
```
color.component.button.primary.background.default.light
```

**正确示例：**
```
color.interactive.default
```

**建议：**
- 保持 token 层级在 2-4 层
- 优先使用语义而非组件特定 token

### ❌ 陷阱 2：硬编码值混用

**错误做法：**
```
某些组件用 token，某些组件用硬编码颜色
```

**正确做法：**
```
100% 使用 token，0 硬编码
```

**实施：**
- 设置 Figma 文件规则检查
- Code review 时检查硬编码

### ❌ 陷阱 3：忽略无障碍

**必须检查：**
- 文本颜色对比度 ≥ 4.5:1 (正文)
- 文本颜色对比度 ≥ 3:1 (大文本 18px+)
- 交互元素颜色对比度 ≥ 3:1

**工具：**
- Figma Plugin: Contrast
- WebAIM Contrast Checker
- Chrome DevTools Lighthouse

### ❌ 陷阱 4：token 命名不一致

**错误示例：**
```
color.textPrimary
color.text-secondary
color.text_tertiary
```

**正确示例：**
```
color.text.primary
color.text.secondary
color.text.tertiary
```

### ❌ 陷阱 5：缺少文档

**必须文档化：**
- 每个 token 的用途
- 使用场景示例
- Do's and Don'ts
- 废弃 token 的替代方案

---

## 📊 成功指标

### 实施前 vs. 实施后

| 指标 | 实施前 | 目标 |
|------|--------|------|
| 独立颜色数量 | ~50+ | ≤30 (原始色) + 语义映射 |
| 字体大小数量 | 不规范 | 12 个标准尺寸 |
| 设计-开发一致性 | ~70% | 95%+ |
| 新组件设计时间 | 2-4 小时 | 1-2 小时 |
| 主题切换支持 | 无 | 深色/浅色模式 |
| 代码中硬编码颜色 | ~40% | 0% |

### KPI

- **Token 覆盖率：** ≥95% 组件使用 token
- **一致性评分：** Figma 设计 vs. 代码实现 ≥95% 匹配
- **维护效率：** 全局颜色调整时间 < 10分钟
- **开发效率：** 新组件开发时间减少 30%+

---

## 🎓 培训材料

### 设计师培训（1-2 小时）

**主题 1: Token 概念入门 (30min)**
- 什么是 Design Token？
- 为什么需要 Token？
- Token vs. 硬编码值

**主题 2: 在 Figma 中使用 Token (30min)**
- 如何应用变量到组件
- 如何创建/编辑 token
- 模式（Modes）的使用

**主题 3: 实战演练 (30min)**
- 创建一个新按钮组件
- 应用正确的 token
- 测试深色模式

### 开发者培训（1 小时）

**主题 1: Token 系统架构 (20min)**
- 原始 token vs. 语义 token
- Token 命名规范
- 导出格式说明

**主题 2: 在代码中使用 Token (20min)**
- CSS Variables
- 平台特定实现（iOS/Android/Web）
- 动态主题切换

**主题 3: 同步流程 (20min)**
- 如何获取最新 token
- 变更通知机制
- 版本管理

---

## 📞 支持和资源

### 内部资源
- **Figma 文件：** [链接到设计系统文件]
- **Token 文档：** [链接到文档页面]
- **GitHub Repo：** [链接到代码仓库]
- **Slack 频道：** #design-system
- **负责人：** @design-lead @tech-lead

### 外部资源
- [Design Tokens W3C 社区组](https://www.w3.org/community/design-tokens/)
- [Material Design 3](https://m3.material.io/)
- [Ant Design Token System](https://ant.design/docs/spec/tokens)
- [Shopify Polaris Tokens](https://polaris.shopify.com/tokens/colors)

---

## ✅ 快速检查清单

在提交任何 token 变更前，确认：

- [ ] 命名符合规范（category.subcategory.variant）
- [ ] 已添加描述说明
- [ ] 已在 2+ 组件中测试
- [ ] 深色模式已验证（如适用）
- [ ] 对比度符合 WCAG AA 标准
- [ ] 文档已更新
- [ ] 变更日志已记录
- [ ] 开发团队已通知
- [ ] 破坏性变更已标注
- [ ] 废弃 token 已提供迁移路径

---

## 🎉 总结

完整实施这套 Token 系统后，你将获得：

✅ **设计一致性** - 所有产品使用统一的设计语言
✅ **开发效率** - 开发者无需猜测颜色、间距等
✅ **易于维护** - 全局调整只需修改 token
✅ **主题支持** - 轻松实现深色模式等主题
✅ **可扩展性** - 新增组件自动继承设计系统
✅ **无障碍** - 内置对比度检查保证可访问性
✅ **自动化** - 设计变更自动同步到代码

立即开始，从审计现有设计开始你的 Token 之旅！
