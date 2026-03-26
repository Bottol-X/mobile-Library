# Figma Variables 快速操作步骤

## ⚡ 5 分钟快速版

### Step 1: 打开 Variables 面板
```
快捷键: Option/Alt + Command/Ctrl + K
或: 右侧面板 → Design → Variables 图标
```

---

### Step 2: 创建原始颜色 (2 分钟)

**创建 Collection:**
1. 点击 "+" → Create collection
2. 命名: `Primitives/Color`

**创建变量:**
```
点击 "+" → 选择 Color 类型

brand/primary/500    #3387FF    [主品牌色]
brand/primary/600    #0066FF
neutral/0            #FFFFFF
neutral/900          #171717
neutral/1000         #0F1721
```

**快捷方式:** 创建一个后按 Cmd/Ctrl+D 复制，修改名称和值

---

### Step 3: 创建语义颜色 (2 分钟)

**创建 Collection:**
1. 点击 "+" → Create collection
2. 命名: `Semantic/Color`

**创建并映射变量:**
```
点击 "+" → 选择 Color 类型

变量名: text/primary
点击颜色值 → 点击🔗Variables图标 → 选择 neutral/1000 → 设置透明度 90%

变量名: background/primary
点击颜色值 → 点击🔗Variables图标 → 选择 neutral/0

变量名: interactive/default
点击颜色值 → 点击🔗Variables图标 → 选择 brand/primary/500
```

---

### Step 4: 添加深色模式 (1 分钟)

**在 Semantic/Color 中:**
1. 点击 "..." → Edit collection
2. Modes → 点击 "+" → 命名 "Dark"
3. 切换到 Dark mode
4. 重新映射：
   - `text/primary` → `neutral/0` (90%)
   - `background/primary` → `neutral/900`

---

### Step 5: 应用到组件 (<1 分钟)

**应用颜色:**
1. 选中组件
2. Fill → 点击颜色 → 🔗Variables → 选择 `interactive/default`

**测试模式切换:**
1. 创建 Frame
2. 右侧 Layer → Variables → 选择 Light/Dark

✅ 完成！

---

## 🎯 核心映射关系

```
原始变量                    语义变量                    组件应用
────────────────────────────────────────────────────────────

brand/primary/500    →     interactive/default    →    Button Fill
    #3387FF                     (引用)                   (使用)

neutral/1000 90%     →     text/primary          →    Text Color
    #0F1721                     (引用)                   (使用)

spacing/4            →     component/lg          →    Button Padding
    16px                        (引用)                   (使用)
```

---

## 📋 命名速查

### 原始变量命名
```
✅ brand/primary/500
✅ neutral/900
✅ spacing/4
✅ radius/md

❌ 主品牌色
❌ color-brand-primary-500
❌ spacing_16px
```

### 语义变量命名
```
✅ text/primary
✅ background/elevated
✅ interactive/hovered
✅ component/lg

❌ textPrimary
❌ bg-elevated
❌ hover-color
```

---

## 🎨 最小可行集合

**只有 1 小时？创建这些：**

### Primitives/Color
```
brand/primary/500    #3387FF
neutral/0            #FFFFFF
neutral/900          #171717
```

### Semantic/Color (Light)
```
text/primary         → {neutral/900} 90%
background/primary   → {neutral/0}
interactive/default  → {brand/primary/500}
```

### Semantic/Color (Dark)
```
text/primary         → {neutral/0} 90%
background/primary   → {neutral/900}
interactive/default  → {brand/primary/500}
```

这就够用了！其他可以逐步补充。

---

## 🚨 常见错误

### ❌ 错误 1: 语义变量直接填颜色值
```
❌ text/primary = #0F1721

✅ text/primary → {neutral/1000}
```

### ❌ 错误 2: 组件使用原始变量
```
❌ Button Fill = {brand/primary/500}

✅ Button Fill = {interactive/default}
```

### ❌ 错误 3: 变量类型不匹配
```
❌ Fill (需要 Color) ← 选择了 Number 变量

✅ Fill (需要 Color) ← 选择 Color 变量
```

### ❌ 错误 4: 深色模式直接复制浅色值
```
❌ Dark mode 的 text/primary → {neutral/1000} (太暗)

✅ Dark mode 的 text/primary → {neutral/0} (白色文本)
```

---

## 🔍 检查清单

在提交设计前检查：

- [ ] 所有组件使用的是**语义变量**而非硬编码
- [ ] 语义变量都**映射到原始变量**
- [ ] 深浅模式切换**颜色正常**
- [ ] 对比度符合 **WCAG AA 标准**（4.5:1）
- [ ] 变量命名**符合规范**（小写 + 斜杠分隔）
- [ ] 添加了**变量描述**说明用途

---

## 💡 专业技巧

### 技巧 1: 使用颜色插件生成色阶
```
安装插件: Color Shades Generator
输入主色: #3387FF
自动生成: 100-900 色阶
```

### 技巧 2: 批量检查变量使用
```
选中变量 → 右侧显示 "Used in X layers"
点击查看所有使用位置
```

### 技巧 3: 变量搜索
```
Variables 面板顶部有搜索框
输入: "primary" 快速找到所有相关变量
```

### 技巧 4: 快速切换 Mode 预览
```
选中 Frame
快捷键: Cmd/Ctrl + Shift + M
快速切换 Light/Dark 模式
```

### 技巧 5: 导出为 Styles（兼容旧版）
```
选中使用变量的图层
右键 → Create style
让老项目也能使用变量系统
```

---

## 🎓 学习路径

### 第 1 天: 理解概念
- [ ] 阅读完整操作指南
- [ ] 理解原始 vs. 语义变量
- [ ] 了解 Modes 工作原理

### 第 2 天: 创建基础
- [ ] 创建原始颜色变量（10 个）
- [ ] 创建语义颜色变量（10 个）
- [ ] 建立映射关系

### 第 3 天: 添加深色模式
- [ ] 添加 Dark Mode
- [ ] 重新映射所有颜色
- [ ] 测试组件切换

### 第 4-5 天: 完整系统
- [ ] 添加间距、圆角变量
- [ ] 更新所有组件使用变量
- [ ] 创建文档页面

### 第 6-7 天: 导出和同步
- [ ] 导出 JSON Token
- [ ] 集成到开发流程
- [ ] 建立自动化工作流

---

## 📞 需要帮助？

**常见问题快速解决：**

| 问题 | 解决方案 |
|------|----------|
| 找不到变量图标 | 检查属性类型是否匹配（Color/Number） |
| 无法映射变量 | 确保 Collection 已创建且有变量 |
| 模式切换无效 | 检查 Frame 是否正确应用了 Mode |
| 变量丢失 | 检查 Library 是否启用 |
| 对比度不足 | 使用 Contrast 插件检查 |

**进阶资源：**
- Figma 官方文档: [figma.com/best-practices/variables](https://help.figma.com/hc/en-us/articles/15339657135383-Guide-to-variables-in-Figma)
- 社区案例: Figma Community 搜索 "Variables"
- 视频教程: YouTube 搜索 "Figma Variables Tutorial"

---

## 🚀 下一步行动

完成变量设置后：

1. **✅ 立即行动:** 更新 3 个核心组件（Button, Input, Card）
2. **📅 本周目标:** 完成所有组件迁移
3. **🎯 下周目标:** 导出 JSON 并同步到代码
4. **🏆 本月目标:** 建立完整的设计-开发工作流

---

**记住：** 完美的 Token 系统不是一天建成的，先建立核心变量，逐步完善！

开始你的第一个变量吧！🎨✨
