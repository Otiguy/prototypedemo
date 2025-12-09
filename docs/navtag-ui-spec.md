# NavTag 产品UI样式规范（v1.0）

## 概述
- 视觉基调：深色赛博霓虹风格，蓝色为主色，橙色强调。
- 字体体系：标题使用 `Orbitron`，正文使用 `Poppins`。
- 风格要点：玻璃态（模糊+半透明）、圆角层级、发光阴影、顺滑动效。
- 参考实现：页面样式见 `prototype-interactive.html`（例如标题与按钮：`prototype-interactive.html:115-160`；地图弹窗：`prototype-interactive.html:592-624`）。

## 设计令牌（Design Tokens）
- 颜色
  - 背景：`--color-bg-0: #0A0E17`，`--color-bg-1: #0D111A`，`--color-bg-2: #1A1F2B`
  - 主色：`--color-primary: #3A8BFF`；强调：`--color-accent: #FF9E4A`
  - 渐变辅助：`--color-primary-strong: #2563eb`，`--color-primary-light: #60A5FA`
  - 文本：`--color-text: #FFFFFF`；次文：`--color-text-muted: #8B94A4`
  - 状态：`--color-success: #22C55E`，`--color-error: #EF4444`
- 字体
  - 标题：`Orbitron`（全大写、加字距）；正文：`Poppins`
- 间距（px）
  - `--space-1: 4`，`--space-2: 8`，`--space-3: 12`，`--space-4: 16`，`--space-5: 20`，`--space-6: 24`，`--space-7: 28`，`--space-8: 32`，`--space-9: 40`
- 圆角（px）
  - `--radius-lg: 28`，`--radius-md: 24`，`--radius-sm: 20`，`--radius-xs: 12`
- 阴影/发光
  - 霓虹发光：`rgba(58,139,255,0.4–0.8)`；深度阴影：`0 20px 60px rgba(0,0,0,0.6)`
- 动效时序
  - 过渡：`0.3s ease`；抽屉/弹窗：`0.3–0.4s`；呼吸/脉冲：`2s–2.5s`

## 排版规范
- 标题
  - 主标题 `.title-primary`：`32px/700/uppercase/letter-spacing: 3px`（`prototype-interactive.html:115-122`）
  - 次标题 `.title-secondary`：`24px/600/letter-spacing: 1.5px`（`prototype-interactive.html:124-129`）
  - Section Header `.section-header`：`28px/700/uppercase/3px`，渐变背景+发光（`prototype-interactive.html:31-46`）
- 正文 `.text-body`
  - 字号 `15px`，行高 `1.6`，次文色（`prototype-interactive.html:131-135`）
- 文案规则
  - 标题与按钮尽量使用大写并增加字距；次要说明用次文色。

## 布局与间距
- 容器内边距常用 `20px`；列表项垂直间距 `8–12px`。
- 栅格
  - 图标选择：6 列、间距 `12px`（`prototype-interactive.html:850-858`）
  - 地图控件列：右侧纵向 `12px`（`prototype-interactive.html:671-679`）

## 组件规范
- 按钮
  - 主按钮 `.btn-primary`：蓝色渐变、`24px` 圆角、发光与悬停上浮、可选 `.btn-breathing`（`prototype-interactive.html:138-160, 176-184, 186-201`）
  - 次按钮 `.btn-secondary`：半透明蓝背景、蓝色文字、弱发光（`prototype-interactive.html:203-224`）
- 输入框 `.input-field`
  - 玻璃态背景、`20px` 圆角、占位符次文色、聚焦发光（`prototype-interactive.html:226-247`）
- 卡片 `.glass-card`
  - 半透明 + 模糊 + 细蓝边 + 阴影（`prototype-interactive.html:249-257`）
- 列表项 `.tag-item`
  - 玻璃态列表项，滑动露出 `.action-btn`；边缘发光引导 `.tag-item-content::after`（`prototype-interactive.html:260-316, 1017-1034`）
- 抽屉 `.drawer`
  - 底部上拉，玻璃态背景、顶部大圆角，`handle` 控制高度（`prototype-interactive.html:645-667, 2230-2240`）
- 地图控件 `.map-controls .control-btn`
  - 玻璃态方按钮，`44x44`，蓝色 hover 发光（`prototype-interactive.html:671-699`）
- Toast `.toast`
  - 顶部居中，玻璃态背景；`success/error` 边框色（`prototype-interactive.html:724-755`）
- Modal `.modal-overlay/.modal-content`
  - 全屏玻璃遮罩，弹窗深色渐变，`28px` 圆角，重阴影（`prototype-interactive.html:369-401`）
- 用户中心
  - 左侧抽屉，菜单 hover 左侧蓝色指示线（`prototype-interactive.html:1089-1174`）

## 动效规范
- 进入/退出：`fadeIn` 0.3–0.5s（`prototype-interactive.html:386-389, 1012-1015`）
- 呼吸发光：`breathing` 2.5s（按钮）
- 脉冲：徽标/铃铛等 `pulse` 2s（`prototype-interactive.html:428-441, 2459-2472`）
- 扫描：扫描波 `scanWave` 与扫描线 `scanLine`（`prototype-interactive.html:488-499, 951-954`）
- 滑动：列表项横向 `translateX` 带阈值与回弹（`prototype-interactive.html:2246-2352`）

## 图标与地图
- 图标：Lucide 图标统一大小与颜色（控件 `18px`，蓝色主色）。
- 地图（Leaflet）
  - 标尺与弹窗做深色/蓝色定制；用户为蓝色脉冲圆点，标签用橙色圆标（`prototype-interactive.html:556-590, 592-624, 516-554`）。

## 可访问性
- 触控目标建议最小 `44x44`（地图控件已满足）。
- 对比度：深色背景与白色/蓝色文字确保可读性；错误/成功状态使用高饱和色。
- 键盘与屏幕阅读器：为交互元素提供可聚焦与语义标签（后续代码层实施）。

## 使用建议
- 在页面 `<head>` 中引入 `styles/navtag-ui.css`（当前已引入，见 `prototype-interactive.html:1293-1298` 附加链接）。
- 统一使用令牌变量替换硬编码颜色与尺寸，逐步将内联 `style="..."` 迁移为类名。
- 常用组件建议直接使用已定义类（如 `.btn-primary`、`.input-field`、`.drawer`、`.toast`）。

## 版本与维护
- 当前版本：`v1.0`。建议后续按需扩展变量（如亮色主题）与组件状态（禁用/加载）。

## 颜色用色规范
- 调色盘定义
  - 主色（Primary）：`#3A8BFF`，用于主按钮、强调文本与发光（如 `.btn-primary` 渐变，`prototype-interactive.html:141-154`）
  - 主色渐变端点：`#2563eb`（深端）、`#60A5FA`（浅端）用于悬停/边框/光晕（`prototype-interactive.html:169, 176-184`）
  - 中性背景：`#0A0E17`、`#0D111A`、`#1A1F2B` 按层级由浅到深应用（页面/容器/弹窗，`prototype-interactive.html:21-29, 392-400`）
  - 文本：主文 `#FFFFFF`，次文 `#8B94A4`（`prototype-interactive.html:118-135, 133`）
  - 强调色（Accent/警示）：橙色 `#FF9E4A`，用于标签标记/中等级提示（`prototype-interactive.html:540-554, 846-847`）
  - 状态色：成功 `#22C55E`、错误 `#EF4444`（Toast/强度标识，`prototype-interactive.html:749-755, 845-847`）

- 角色与场景映射
  - 交互主控：主按钮、主要图标、地图控件边框与 hover 发光统一使用主色（`prototype-interactive.html:671-699`）
  - 信息层次：
    - 一级信息：白色；二级说明/时间/地址：次文色（`prototype-interactive.html:118-135, 1755-1758`）
    - 重要数值/距离：主色强调（`prototype-interactive.html:1760-1761, 639-643`）
  - 警示/中等级反馈：橙色用于标签标记与“中等强度”提示；错误使用红色，成功使用绿色（`prototype-interactive.html:845-847, 749-755`）

- 渐变与发光使用
  - 渐变应用在主按钮与扫描/框线效果，建议端点为主色→深端；浅端用于 hover 提升（`prototype-interactive.html:141-154, 951-954`）
  - 发光规范：蓝色光晕 `rgba(58,139,255,0.3–0.8)`；悬停时提升到 `0.6–0.8`，静态为 `0.3–0.4`（`prototype-interactive.html:153-160, 176-184`）

- 透明度与玻璃态
  - 玻璃背景透明度建议：`0.4–0.8`，常用 `0.6`；抽屉/Toast/控件使用 `0.7–0.95` 增强可读性（`prototype-interactive.html:651-660, 724-742`）
  - 半透明边框：主色 `alpha 0.2–0.4`，hover 到 `0.5–0.6`（`prototype-interactive.html:206-214, 221-224`）

- 透明度细则（组件级）
  - 页面背景：线性渐变纯色，无透明度；容器内采用玻璃态时使用 `rgba(26,31,43,0.4–0.8)`（`prototype-interactive.html:249-257, 260-267`）
  - 控件背景（`icon-btn`/`control-btn`）：`rgba(26,31,43,0.6–0.7)`；hover 叠加轻度发光（`prototype-interactive.html:681-699, 703-722`）
  - 抽屉背景：`rgba(26,31,43,0.95)` 顶部；叠加模糊，保证文字对比（`prototype-interactive.html:651-660`）
  - 遮罩层（Modal Overlay）：`rgba(13,17,26,0.85)`，确保下层内容被弱化（`prototype-interactive.html:369-381`）
  - Toast 背景：`rgba(26,31,43,0.95)`；边框随状态色变化（`prototype-interactive.html:724-755`）
  - 列表项边框：`rgba(58,139,255,0.15)` 默认，`0.4–0.6` 在 hover/active（`prototype-interactive.html:260-367`）
  - 边缘引导发光：蓝色光条 `edgeGlow` 建议透明度在 `0.6–1.0` 范围动画（`prototype-interactive.html:288-316`）
  - 地图标记发光：用户标记 `0.8–1.0` 强光；标签标记 `0.6–0.8`（`prototype-interactive.html:521-535, 547-554`）
  - 扫描效果：框线/扫描线使用透明渐变（`prototype-interactive.html:941-954`）

- 建议变量（可选）
  - `alpha-glass-bg: 0.6`、`alpha-overlay: 0.85`、`alpha-control-bg: 0.7`、`alpha-toast-bg: 0.95`
  - `alpha-border-default: 0.2`、`alpha-border-hover: 0.5`、`alpha-glow-static: 0.4`、`alpha-glow-hover: 0.7`
  - 后续可在 CSS 中统一由令牌控制透明度，以便主题切换与暗/亮模式适配。

- 地图专用规范
  - 用户标记：主色脉冲圆点（`prototype-interactive.html:516-535`）
  - 标签标记：橙色圆标 + 悬停放大与增强发光（`prototype-interactive.html:537-554`）
  - 弹窗与标尺：深色背景 + 主色边框与文字（`prototype-interactive.html:556-590, 592-624`）

- 文本与链接
  - 链接颜色：主色，hover 使用浅端色并加下划线（`prototype-interactive.html:774-784`）
  - 代码/等宽信息：使用白色配合等宽字体增强区分（如 MAC/版本，`prototype-interactive.html:2729-2736, 1259-1263`）

- 状态与交互
  - hover：提高背景透明度与边框 alpha，并增加发光强度或位移（`prototype-interactive.html:221-224, 697-700, 1065-1069`）
  - focus：输入框边框从 `alpha 0.2` 提升至 `0.6`，并加轻微蓝色光晕（`prototype-interactive.html:243-247`）
  - active：主按钮归位，无发光增强，防止误导（`prototype-interactive.html:182-184`）
  - disabled：降低不透明度至 `0.5`，禁用 pointer（计时按钮示例，`prototype-interactive.html:1904-1923`）

- 对比与无障碍
  - 在深色背景上保持文字与控件的对比度≥4.5:1；次文色仅用于辅助信息，不用于主要交互。
  - 错误/成功等状态色与深色背景对比充足；橙色用于警示而非主交互，避免与主色竞争。
