# Design Token 快速参考手册

## 🎯 Token 速查表

### 颜色 Token

#### 文本颜色
```
color.text.primary       主要文本（标题、重要内容）
color.text.secondary     次要文本（描述、辅助信息）
color.text.tertiary      三级文本（提示、不重要信息）
color.text.disabled      禁用文本
color.text.inverse       深色背景上的文本
color.text.link          链接文本
color.text.success       成功状态文本
color.text.warning       警告状态文本
color.text.error         错误状态文本
```

#### 背景颜色
```
color.background.primary     主背景（页面背景）
color.background.secondary   次级背景（区域背景）
color.background.tertiary    三级背景（卡片内背景）
color.background.elevated    浮起背景（弹窗、卡片）
color.background.overlay     遮罩背景
color.background.inverse     反色背景（深色区域）
```

#### 边框颜色
```
color.border.default         默认边框
color.border.strong          强边框（需要明显分隔）
color.border.subtle          弱边框（微妙分隔）
color.border.interactive     可交互边框（输入框）
color.border.focus           聚焦边框
color.border.error           错误边框
```

#### 交互颜色
```
color.interactive.default    默认交互色
color.interactive.hovered    悬停交互色
color.interactive.pressed    按下交互色
color.interactive.disabled   禁用交互色
```

#### 图标颜色
```
color.icon.primary           主要图标
color.icon.secondary         次要图标
color.icon.tertiary          三级图标
color.icon.disabled          禁用图标
color.icon.inverse           反色图标
color.icon.interactive       可交互图标
```

---

### 排版 Token

#### 展示文字（Display）
```
typography.display.large     48px/bold - 启动页、营销页大标题
typography.display.medium    40px/bold - 营销页中标题
typography.display.small     32px/bold - 营销页小标题
```

#### 标题（Headline）
```
typography.headline.h1       28px/bold - 页面主标题
typography.headline.h2       24px/bold - 区块标题
typography.headline.h3       20px/semibold - 子区块标题
```

#### 小标题（Title）
```
typography.title.t1          18px/semibold - 弹窗标题
typography.title.t2          16px/semibold - 导航栏标题、卡片标题
typography.title.t3          14px/semibold - 列表项标题
```

#### 正文（Body）
```
typography.body.large        16px/regular - 重要正文
typography.body.base         14px/regular - 标准正文
typography.body.small        12px/regular - 小正文

typography.body.large.emphasis   16px/medium - 强调大正文
typography.body.base.emphasis    14px/medium - 强调正文
typography.body.small.emphasis   12px/medium - 强调小正文
```

#### 说明文字（Caption）
```
typography.caption.c1        12px/regular - 说明文字、时间戳
typography.caption.c2        11px/regular - 标签、表单标签
typography.caption.c3        10px/regular - 底部标签栏文字、徽标
```

#### 交互文字（Interactive）
```
typography.interactive.button.large   16px/medium - 大按钮
typography.interactive.button.medium  14px/medium - 中按钮
typography.interactive.button.small   12px/medium - 小按钮
typography.interactive.link           14px/regular - 链接
typography.interactive.label          12px/medium - 输入框标签
```

---

### 间距 Token

#### 数字间距（4px 网格）
```
spacing.0     0px
spacing.1     4px      极小间距（图标内边距）
spacing.2     8px      小间距（标签内边距）
spacing.3     12px     中小间距（按钮内边距）
spacing.4     16px     中间距（卡片内边距）
spacing.5     20px     大间距（按钮水平内边距）
spacing.6     24px     超大间距（卡片上下间距）
spacing.8     32px     区块间距
spacing.10    40px     大区块间距
spacing.12    48px     页面边距
spacing.16    64px     特大区块间距
```

#### 语义间距
```
// 组件内间距
spacing.component.xs     4px      最小间距
spacing.component.sm     8px      小间距
spacing.component.md     12px     中间距
spacing.component.lg     16px     大间距
spacing.component.xl     20px     超大间距

// 布局间距
spacing.layout.xs        12px     最小布局间距
spacing.layout.sm        16px     小布局间距
spacing.layout.md        24px     中布局间距
spacing.layout.lg        32px     大布局间距
spacing.layout.xl        48px     超大布局间距

// 区块间距
spacing.section.sm       24px     小区块间距
spacing.section.md       32px     中区块间距
spacing.section.lg       48px     大区块间距
spacing.section.xl       64px     超大区块间距
```

---

### 圆角 Token

#### 数字圆角
```
radius.none     0px
radius.xs       2px      最小圆角（小标签）
radius.sm       4px      小圆角（标签、徽标）
radius.base     6px      基础圆角
radius.md       8px      中圆角（按钮、输入框）
radius.lg       12px     大圆角（卡片）
radius.xl       16px     超大圆角（弹窗）
radius.2xl      20px     二级超大
radius.3xl      24px     三级超大
radius.full     9999px   完全圆角（头像、圆形按钮）
```

#### 语义圆角
```
radius.component.button      8px      按钮圆角
radius.component.card        12px     卡片圆角
radius.component.modal       16px     弹窗圆角
radius.component.tag         4px      标签圆角
radius.component.input       8px      输入框圆角
radius.component.avatar      full     头像圆角
```

---

### 阴影 Token

```
shadow.none                  无阴影
shadow.xs                    0 1px 2px rgba(0,0,0,0.05) - 最小阴影
shadow.sm                    0 1px 3px rgba(0,0,0,0.1) - 小阴影
shadow.base                  0 2px 4px rgba(0,0,0,0.1) - 基础阴影
shadow.md                    0 4px 6px rgba(0,0,0,0.1) - 中阴影
shadow.lg                    0 10px 15px rgba(0,0,0,0.1) - 大阴影
shadow.xl                    0 20px 25px rgba(0,0,0,0.1) - 超大阴影
shadow.2xl                   0 25px 50px rgba(0,0,0,0.15) - 二级超大

// 组件阴影
shadow.component.button      基础阴影
shadow.component.card        中阴影
shadow.component.modal       超大阴影
shadow.component.dropdown    大阴影
shadow.component.toast       大阴影
shadow.component.nav         小阴影
```

---

### 尺寸 Token

#### 组件高度
```
size.height.xs       24px     最小高度（小标签）
size.height.sm       28px     小高度（小按钮）
size.height.base     32px     基础高度（输入框）
size.height.md       36px     中高度（中按钮）
size.height.lg       40px     大高度（大按钮）
size.height.xl       44px     超大高度（导航栏）
size.height.2xl      48px     二级超大
size.height.3xl      56px     三级超大
```

#### 图标尺寸
```
size.icon.xs         12px     最小图标
size.icon.sm         16px     小图标
size.icon.base       20px     基础图标
size.icon.md         24px     中图标
size.icon.lg         28px     大图标
size.icon.xl         32px     超大图标
size.icon.2xl        40px     二级超大图标
```

#### 头像尺寸
```
size.avatar.xs       24px     最小头像
size.avatar.sm       32px     小头像
size.avatar.base     40px     基础头像
size.avatar.md       48px     中头像
size.avatar.lg       64px     大头像
size.avatar.xl       80px     超大头像
size.avatar.2xl      96px     二级超大头像
```

---

### Z-index Token

```
elevation.base       0        基础层
elevation.raised     1        微升层（卡片悬浮效果）
elevation.dropdown   10       下拉层（下拉菜单）
elevation.sticky     100      粘性层（固定在滚动区域）
elevation.fixed      200      固定层（顶部导航栏）
elevation.modal      300      弹窗层（对话框）
elevation.popover    400      气泡层（Popover、Tooltip）
elevation.toast      500      Toast 层
elevation.tooltip    600      Tooltip 层
elevation.max        999      最高层（调试用）
```

---

### 动画 Token

#### 持续时间
```
motion.duration.instant      100ms    瞬间（微反馈）
motion.duration.fast         200ms    快速（hover 效果）
motion.duration.base         300ms    基础（默认过渡）
motion.duration.slow         400ms    缓慢（页面切换）
motion.duration.slower       500ms    更慢（复杂动画）
```

#### 缓动函数
```
motion.ease.linear           linear
motion.ease.in               ease-in
motion.ease.out              ease-out
motion.ease.inOut            ease-in-out
motion.ease.sharp            cubic-bezier(0.4, 0.0, 0.6, 1)
motion.ease.standard         cubic-bezier(0.4, 0.0, 0.2, 1)
motion.ease.emphasized       cubic-bezier(0.0, 0.0, 0.2, 1)
```

---

## 🎨 使用场景速查

### 按钮设计

```
【主按钮 Primary Button】
背景：color.interactive.default
文字：color.text.inverse
圆角：radius.component.button (8px)
高度：size.height.lg (40px) / size.height.md (36px) / size.height.base (32px)
内边距：spacing.3 (12px) spacing.5 (20px)
字体：typography.interactive.button.medium
阴影：shadow.component.button

状态：
- Hovered: bg → color.interactive.hovered
- Pressed: bg → color.interactive.pressed
- Disabled: bg → color.interactive.disabled, text → color.text.disabled
```

```
【次按钮 Secondary Button】
背景：transparent
边框：1px solid color.border.default
文字：color.text.primary
其他同主按钮

状态：
- Hovered: bg → color.surface.hovered
- Pressed: bg → color.surface.pressed
- Disabled: border → color.border.subtle, text → color.text.disabled
```

```
【文字按钮 Text Button】
背景：transparent
文字：color.interactive.default
内边距：spacing.2 (8px) spacing.4 (16px)

状态：
- Hovered: bg → color.surface.hovered
- Pressed: bg → color.surface.pressed
- Disabled: text → color.text.disabled
```

---

### 卡片设计

```
【基础卡片】
背景：color.background.elevated
边框：1px solid color.border.subtle (可选)
圆角：radius.component.card (12px)
内边距：spacing.6 (24px) 或 spacing.4 (16px)
阴影：shadow.component.card

【可点击卡片】
基础 + 状态：
- Hovered: shadow.md + bg → color.surface.hovered
- Pressed: shadow.sm
```

---

### 输入框设计

```
【输入框 Input】
背景：color.background.primary
边框：1px solid color.border.default
圆角：radius.component.input (8px)
高度：size.height.base (32px) / size.height.lg (40px)
内边距：spacing.3 (12px) spacing.4 (16px)
字体：typography.body.base
占位符：color.text.tertiary

状态：
- Focus: border → color.border.focus (2px)
- Error: border → color.border.error
- Disabled: bg → color.surface.disabled, text → color.text.disabled
```

---

### 导航栏设计

```
【顶部导航栏】
背景：color.background.elevated
高度：size.height.xl (44px) / size.height.3xl (56px)
标题：typography.title.t2
阴影：shadow.component.nav
z-index：elevation.fixed

【底部标签栏】
背景：color.background.elevated
高度：size.height.3xl (56px)
图标：size.icon.md (24px)
文字：typography.caption.c3
z-index：elevation.fixed
```

---

### 列表设计

```
【列表项 List Item】
高度：size.height.2xl (48px) / size.height.3xl (56px) / auto
内边距：spacing.4 (16px)
边框：1px solid color.border.subtle (底部)

标题：typography.title.t3
描述：typography.caption.c1, color.text.secondary
图标：size.icon.base (20px), color.icon.secondary

状态：
- Hovered: bg → color.surface.hovered
- Pressed: bg → color.surface.pressed
- Selected: bg → color.surface.selected
```

---

### 弹窗设计

```
【对话框 Modal】
背景：color.background.elevated
圆角：radius.component.modal (16px)
内边距：spacing.6 (24px)
阴影：shadow.component.modal
z-index：elevation.modal

标题：typography.title.t1
内容：typography.body.base
按钮：spacing.4 (16px) 间距

【遮罩层】
背景：color.background.overlay (50% opacity)
z-index：elevation.modal - 1
```

---

### 标签/徽标设计

```
【标签 Tag】
背景：color.surface.default
圆角：radius.component.tag (4px)
高度：size.height.xs (24px)
内边距：spacing.1 (4px) spacing.2 (8px)
字体：typography.caption.c2
```

```
【徽标 Badge】
背景：color.semantic.error.500
圆角：radius.full
最小宽度：size.height.xs (24px)
高度：size.height.xs (24px)
内边距：spacing.1 (4px)
字体：typography.caption.c3, color.text.inverse
```

---

## 📝 命名检查表

在创建/使用 Token 时，检查：

✅ **命名结构正确**
- [ ] 使用小写字母
- [ ] 使用点号 `.` 分隔
- [ ] 层级不超过 4 层
- [ ] 没有使用缩写（除非行业标准）

✅ **语义化**
- [ ] 名称描述用途而非外观
- [ ] 使用 primary/secondary/tertiary 而非 light/dark
- [ ] 使用 default/hovered/pressed 而非 normal/hover/active

✅ **一致性**
- [ ] 与现有 Token 风格一致
- [ ] 尺度系统一致（xs/sm/base/md/lg/xl）
- [ ] 同类 Token 结构一致

✅ **文档化**
- [ ] 添加描述说明
- [ ] 提供使用示例
- [ ] 标注使用场景

---

## 🚨 常见错误

### ❌ 错误命名

```
❌ color.btnPrimaryBg
✅ color.interactive.default

❌ spacing.16px
✅ spacing.4 (或 spacing.component.lg)

❌ text-large-bold
✅ typography.body.large.emphasis

❌ borderRadius8
✅ radius.md (或 radius.component.button)
```

### ❌ 错误使用

```
❌ 直接使用原始 token
Button bg → color.brand.primary.500
✅ 使用语义 token
Button bg → color.interactive.default

❌ 混用硬编码和 token
Button padding: 12px 20px (hardcoded)
✅ 全部使用 token
Button padding: spacing.3 spacing.5

❌ 忽略状态
Button 只有 default 状态
✅ 完整状态
Button: default, hovered, pressed, disabled
```

---

## 🔍 Token 查找速查

### 我需要...

**文本颜色**
- 主要内容 → `color.text.primary`
- 描述文字 → `color.text.secondary`
- 提示文字 → `color.text.tertiary`
- 禁用文字 → `color.text.disabled`
- 深色背景上的文字 → `color.text.inverse`
- 链接文字 → `color.text.link`

**背景颜色**
- 页面背景 → `color.background.primary`
- 区域背景 → `color.background.secondary`
- 卡片背景 → `color.background.elevated`
- 弹窗背景 → `color.background.elevated`
- 遮罩背景 → `color.background.overlay`

**边框颜色**
- 默认边框 → `color.border.default`
- 输入框边框 → `color.border.interactive`
- 输入框聚焦边框 → `color.border.focus`
- 错误边框 → `color.border.error`

**间距**
- 按钮内边距 → `spacing.3` (上下) `spacing.5` (左右)
- 卡片内边距 → `spacing.4` 或 `spacing.6`
- 列表项内边距 → `spacing.4`
- 页面边距 → `spacing.4` 或 `spacing.6`
- 组件之间间距 → `spacing.4` 到 `spacing.8`
- 区块之间间距 → `spacing.8` 到 `spacing.16`

**圆角**
- 按钮圆角 → `radius.component.button` (8px)
- 输入框圆角 → `radius.component.input` (8px)
- 卡片圆角 → `radius.component.card` (12px)
- 弹窗圆角 → `radius.component.modal` (16px)
- 标签圆角 → `radius.component.tag` (4px)
- 头像圆角 → `radius.component.avatar` (full)

**字体**
- 页面标题 → `typography.headline.h1`
- 区块标题 → `typography.headline.h2`
- 卡片标题 → `typography.title.t2`
- 列表项标题 → `typography.title.t3`
- 正文内容 → `typography.body.base`
- 说明文字 → `typography.caption.c1`
- 按钮文字 → `typography.interactive.button.medium`

**高度**
- 按钮高度 → `size.height.lg` (40px) 或 `size.height.md` (36px)
- 输入框高度 → `size.height.base` (32px) 或 `size.height.lg` (40px)
- 导航栏高度 → `size.height.xl` (44px) 或 `size.height.3xl` (56px)

**阴影**
- 卡片阴影 → `shadow.component.card`
- 按钮阴影 → `shadow.component.button`
- 弹窗阴影 → `shadow.component.modal`
- 下拉阴影 → `shadow.component.dropdown`

---

## 💡 最佳实践

### 1. 优先使用语义 Token
```
✅ color.text.primary
❌ color.neutral.900
```

### 2. 保持一致性
```
✅ 所有按钮使用相同的 token 组合
❌ 不同按钮使用不同的硬编码值
```

### 3. 考虑深色模式
```
✅ 使用语义 token，自动适配深色模式
❌ 使用固定颜色值
```

### 4. 遵循 8px 网格
```
✅ spacing.4 (16px), spacing.6 (24px)
❌ 15px, 23px
```

### 5. 完整的状态设计
```
✅ default, hovered, pressed, disabled
❌ 只有 default
```

### 6. 无障碍对比度
```
✅ 文本对比度 ≥ 4.5:1
❌ 浅色文本 + 浅色背景
```

---

## 🎯 总结

**记住 3 个原则：**
1. **语义化** - 使用描述用途的名称
2. **一致性** - 遵循命名规范和尺度系统
3. **系统化** - 使用 Token 而非硬编码

**当你不确定时：**
1. 查看这个速查表
2. 参考现有组件
3. 咨询设计系统负责人

**保持 Token 系统健康：**
- 定期审计 Token 使用
- 移除未使用的 Token
- 更新文档和示例
- 版本化重大变更

---

祝你设计愉快！🎨✨
