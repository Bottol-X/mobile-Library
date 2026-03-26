# Figma Variables 映射示例图谱

## 🎨 完整映射关系示意图

```
┌─────────────────────────────────────────────────────────────────────┐
│                          Figma Variables 系统架构                      │
└─────────────────────────────────────────────────────────────────────┘

层级 1: 原始变量 (Primitives)        定义基础值，不直接使用
─────────────────────────────────────────────────────────────────────
Collection: Primitives/Color

brand/primary/500     #3387FF        ← 具体色值
neutral/0             #FFFFFF
neutral/1000          #0F1721
semantic/success/500  #10B981

                        ⬇️ 映射 (Reference)

层级 2: 语义变量 (Semantic)         描述用途，直接使用
─────────────────────────────────────────────────────────────────────
Collection: Semantic/Color (Light Mode)

text/primary          → {neutral/1000} 90%
background/primary    → {neutral/0}
interactive/default   → {brand/primary/500}
text/success          → {semantic/success/500}

                        ⬇️ 应用 (Apply)

层级 3: 组件应用 (Component)        设计实现
─────────────────────────────────────────────────────────────────────
Button Component
├─ Fill               → {interactive/default}
├─ Text color         → {text/inverse}
└─ Border             → {border/interactive}

Card Component
├─ Fill               → {background/elevated}
├─ Title color        → {text/primary}
└─ Body color         → {text/secondary}
```

---

## 📊 颜色系统完整映射

### 品牌色映射

```
原始变量                           语义变量 (Light)              使用场景
──────────────────────────────────────────────────────────────────────

brand/primary/100   #E6F0FF    →  surface/selected      →  选中状态背景
brand/primary/200   #CCE1FF    →  (备用)
brand/primary/300   #99C3FF    →  interactive/disabled  →  禁用按钮 (备选)
brand/primary/400   #66A5FF    →  text/link/visited     →  已访问链接
brand/primary/500   #3387FF    →  interactive/default   →  主按钮背景
                               →  text/link             →  链接文本
                               →  border/focus          →  输入框聚焦边框
brand/primary/600   #0066FF    →  interactive/hovered   →  主按钮悬停
brand/primary/700   #0052CC    →  interactive/pressed   →  主按钮按下
brand/primary/800   #003D99    →  (备用)
brand/primary/900   #002966    →  (备用，深色模式可能用)
```

### 中性色映射

```
原始变量                           语义变量 (Light)              使用场景
──────────────────────────────────────────────────────────────────────

neutral/0      #FFFFFF         →  background/primary    →  页面主背景
                               →  background/elevated   →  卡片背景
                               →  text/inverse          →  深色背景上的文字

neutral/50     #FAFAFA         →  background/secondary  →  区域背景

neutral/100    #F5F5F5         →  background/tertiary   →  输入框背景
                               →  border/subtle         →  微弱分隔线

neutral/200    #E5E5E5         →  border/default        →  默认边框

neutral/300    #D4D4D4         →  border/strong         →  明显分隔线
                               →  interactive/disabled  →  禁用状态

neutral/400    #A3A3A3         →  icon/tertiary         →  不重要图标

neutral/500    #737373         →  (过渡色)

neutral/600    #525252         →  icon/secondary        →  次要图标

neutral/700    #404040         →  text/tertiary         →  提示文本

neutral/800    #262626         →  text/secondary        →  描述文本

neutral/900    #171717         →  text/primary          →  主要文本
                               →  icon/primary          →  主要图标

neutral/1000   #0F1721         →  text/primary (90%)    →  正文文本
                               →  background/inverse    →  深色背景
```

### 功能色映射

```
原始变量                           语义变量                   使用场景
──────────────────────────────────────────────────────────────────────

semantic/success/500  #10B981  →  text/success          →  成功提示文字
                                →  border/success        →  成功状态边框
                                →  icon/success          →  成功图标

semantic/warning/500  #F59E0B  →  text/warning          →  警告提示文字
                                →  border/warning        →  警告状态边框
                                →  icon/warning          →  警告图标

semantic/error/500    #EF4444  →  text/error            →  错误提示文字
                                →  border/error          →  错误状态边框
                                →  icon/error            →  错误图标

semantic/info/500     #3B82F6  →  text/info             →  信息提示文字
                                →  border/info           →  信息状态边框
                                →  icon/info             →  信息图标
```

---

## 🌓 深浅模式映射对比

### 文本颜色

```
变量名称                Light Mode                      Dark Mode
────────────────────────────────────────────────────────────────────

text/primary           {neutral/1000} 90%             {neutral/0} 90%
                       ⬤ #0F1721 (深色文本)            ⬤ #FFFFFF (浅色文本)

text/secondary         {neutral/1000} 60%             {neutral/0} 60%
                       ⬤ #0F1721 (半透明深色)          ⬤ #FFFFFF (半透明浅色)

text/tertiary          {neutral/1000} 45%             {neutral/0} 45%
                       ⬤ #0F1721 (更淡)                ⬤ #FFFFFF (更淡)

text/inverse           {neutral/0}                    {neutral/900}
                       ⬤ #FFFFFF (白色)                ⬤ #171717 (深色)
```

### 背景颜色

```
变量名称                    Light Mode            Dark Mode
─────────────────────────────────────────────────────────────

background/primary         {neutral/0}           {neutral/900}
                           ⬤ #FFFFFF              ⬤ #171717

background/secondary       {neutral/50}          {neutral/800}
                           ⬤ #FAFAFA              ⬤ #262626

background/elevated        {neutral/0}           {neutral/800}
                           ⬤ #FFFFFF              ⬤ #262626

background/inverse         {neutral/900}         {neutral/0}
                           ⬤ #171717              ⬤ #FFFFFF
```

### 交互颜色

```
变量名称                    Light Mode                 Dark Mode
───────────────────────────────────────────────────────────────────

interactive/default        {brand/primary/500}       {brand/primary/400}
                           ⬤ #3387FF (标准亮度)       ⬤ #66A5FF (降低一级)

interactive/hovered        {brand/primary/600}       {brand/primary/300}
                           ⬤ #0066FF (加深)           ⬤ #99C3FF (变浅)

interactive/pressed        {brand/primary/700}       {brand/primary/200}
                           ⬤ #0052CC (更深)           ⬤ #CCE1FF (更浅)
```

**为什么深色模式品牌色要浅一级？**
- 深色背景上，太亮的颜色刺眼
- 浅一级提供更好的可读性
- 保持视觉平衡

---

## 🔢 间距系统映射

```
原始变量                    语义变量                        使用场景
────────────────────────────────────────────────────────────────────

spacing/1     4px      →   component/xs              →   图标内边距
                                                          徽标内边距

spacing/2     8px      →   component/sm              →   小标签内边距
                                                          图标与文字间距

spacing/3     12px     →   component/md              →   按钮垂直内边距
                           layout/xs                 →   卡片元素间距

spacing/4     16px     →   component/lg              →   输入框内边距
                           layout/sm                 →   列表项内边距

spacing/5     20px     →   component/xl              →   按钮水平内边距
                           layout/sm                 →   卡片内边距

spacing/6     24px     →   layout/md                 →   区块间距
                           section/sm                →   小区块间距

spacing/8     32px     →   layout/lg                 →   大区块间距
                           section/md                →   中区块间距

spacing/12    48px     →   layout/xl                 →   页面边距
                           section/lg                →   大区块间距

spacing/16    64px     →   section/xl                →   特大区块间距
```

---

## 🎯 组件级别应用示例

### 示例 1: 主按钮完整映射

```
Component: Button/Primary
─────────────────────────────────────────────────────────────────

属性                        变量                          原始值
─────────────────────────────────────────────────────────────────

Fill (background)          {interactive/default}        #3387FF
                              ↑ 引用
                           {brand/primary/500}

Text color                 {text/inverse}               #FFFFFF
                              ↑ 引用
                           {neutral/0}

Padding horizontal         {spacing/component/xl}       20px
                              ↑ 引用
                           {spacing/5}

Padding vertical           {spacing/component/md}       12px
                              ↑ 引用
                           {spacing/3}

Corner radius              {radius/component/button}    8px
                              ↑ 引用
                           {radius/md}

Height                     40px (固定值，不使用变量)

状态变体：
├─ Default                 Fill: {interactive/default}
├─ Hovered                 Fill: {interactive/hovered}
├─ Pressed                 Fill: {interactive/pressed}
└─ Disabled                Fill: {interactive/disabled}
                           Text: {text/disabled}
```

### 示例 2: 卡片组件映射

```
Component: Card
─────────────────────────────────────────────────────────────────

Frame 属性                  变量                          原始值
─────────────────────────────────────────────────────────────────

Fill (background)          {background/elevated}        #FFFFFF (Light)
                                                        #262626 (Dark)

Stroke (border)            {border/subtle}              #F5F5F5

Corner radius              {radius/component/card}      12px

Padding                    {spacing/layout/md}          24px

Shadow                     手动设置（暂无变量支持）


内部元素：

Title (Text)               {text/primary}               #0F1721 90% (Light)
                                                        #FFFFFF 90% (Dark)

Body (Text)                {text/secondary}             #0F1721 60%

Icon                       {icon/secondary}             #525252

Divider                    {border/default}             #E5E5E5
```

### 示例 3: 输入框映射

```
Component: Input/TextField
─────────────────────────────────────────────────────────────────

属性                        变量                          原始值
─────────────────────────────────────────────────────────────────

Fill (background)          {background/primary}         #FFFFFF

Stroke (border)            {border/default}             #E5E5E5

Stroke (focus)             {border/focus}               #3387FF

Stroke (error)             {border/error}               #EF4444

Corner radius              {radius/component/input}     8px

Padding horizontal         {spacing/component/lg}       16px

Padding vertical           {spacing/component/md}       12px

Text color                 {text/primary}               #0F1721 90%

Placeholder color          {text/tertiary}              #0F1721 45%

Helper text                {text/secondary}             #0F1721 60%

Error text                 {text/error}                 #EF4444
```

---

## 📋 映射检查清单

### ✅ 原始变量检查

- [ ] 所有原始变量都是**具体值**（颜色代码、数字）
- [ ] 原始变量**不引用**其他变量
- [ ] 命名使用**斜杠分隔**（例如：`brand/primary/500`）
- [ ] 颜色使用**标准色阶**（100-900）
- [ ] 添加了**描述说明**

### ✅ 语义变量检查

- [ ] 所有语义变量都**引用原始变量**（显示 `{...}` 格式）
- [ ] 命名描述**用途而非外观**（例如：`text/primary` 而非 `gray/900`）
- [ ] 每个变量有**明确的使用场景**
- [ ] 深浅模式都正确**映射**
- [ ] 添加了**描述说明**

### ✅ 组件应用检查

- [ ] 组件使用**语义变量**而非原始变量
- [ ] 组件使用**语义变量**而非硬编码值
- [ ] 所有颜色都通过**变量应用**（显示 `{...}` 而非 `#...`）
- [ ] 深浅模式切换**正常显示**
- [ ] 所有状态变体都使用**对应变量**

---

## 🎨 快速映射模板

### 新增一个语义颜色变量模板

```
步骤：
1. 在 Semantic/Color Collection 点击 "+"
2. 命名: [category]/[name]
3. 点击颜色值
4. 点击 🔗 Variables 图标
5. 选择 Primitives/Color → [对应原始变量]
6. 设置透明度（如需要）
7. 添加描述
8. 如有深色模式，切换到 Dark mode 重复步骤 3-7

示例：
变量名: text/link
Light mode: {brand/primary/500} 100%
Dark mode: {brand/primary/400} 100%
描述: 链接文本颜色
```

### 新增一个语义间距变量模板

```
步骤：
1. 在 Semantic/Spacing Collection 点击 "+"
2. 命名: [category]/[size]
3. 点击值输入框右侧的变量图标
4. 选择 Primitives/Spacing → [对应数字]
5. 添加描述

示例：
变量名: layout/md
值: {spacing/6} (24px)
描述: 中等布局间距，用于卡片之间
```

---

## 🚀 高效映射技巧

### 技巧 1: 批量创建同类变量

```
1. 创建 text/primary
2. 复制变量 (Cmd/Ctrl + D)
3. 重命名为 text/secondary
4. 修改引用和透明度
5. 继续复制创建 text/tertiary, text/disabled...
```

### 技巧 2: 使用搜索快速定位

```
在 Variables 面板搜索框输入:
- "primary" → 找到所有 primary 相关变量
- "text/" → 找到所有文本变量
- "500" → 找到所有 500 级别的原始变量
```

### 技巧 3: 查看变量使用情况

```
选中变量 → 右侧显示 "Used in X layers"
点击 → 跳转到使用位置
快速检查是否有遗漏或错误使用
```

### 技巧 4: 对比深浅模式

```
创建两个 Frame 并排放置:
Frame 1: 应用 Light mode
Frame 2: 应用 Dark mode
同时预览效果，快速发现映射问题
```

---

## 💡 映射的艺术

**好的映射系统特征：**

✅ **清晰的层级** - 原始 → 语义 → 组件，三层不混淆  
✅ **语义化命名** - 看名字就知道用途  
✅ **完整的覆盖** - 所有场景都有对应变量  
✅ **灵活的扩展** - 新增场景不需要大改  
✅ **易于维护** - 修改原始值，全局自动更新  

**避免的反模式：**

❌ 语义变量直接写颜色值  
❌ 组件直接使用原始变量  
❌ 混用变量和硬编码  
❌ 变量命名描述外观而非用途  
❌ 缺少深色模式映射  

---

**记住核心原则：**

> 原始变量定义"是什么" (What)  
> 语义变量定义"做什么" (Why)  
> 组件应用实现"怎么做" (How)

这样的架构让你的设计系统既强大又优雅！🎨✨
