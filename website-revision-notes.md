# 新站修改意见

审查站点：[新站](http://155.138.214.216:8090/)  
颜色参考：[Vidou](https://vidou.ai/)

## 01｜全站绿色统一为 Vidou 的绿色

**修改范围**  
覆盖全站所有使用绿色的界面元素和素材，包括按钮、图标、徽标、边框、选中高亮及绿色图片素材。用户截图中的 **Pro Version** 按钮是核对示例。

**实现要求**

- 在 Vidou 上检查对应元素的实际样式，获取准确色值。组件有独立的悬停或按下色时，按相同状态对照。
- 优先更新全局主题色变量，并检查组件样式、SVG 和图片素材中是否还有写死的旧绿色，逐一替换。

**验收标准**

- 截图所示的 **Pro Version** 按钮与 Vidou 对应按钮在相同状态下的实际绿色色值一致。
- 检查各页面的绿色按钮、图标及其他绿色素材，确认已采用 Vidou 的对应绿色。

## 02｜首页 AI Video 菜单新增 AI Movie

**修改位置**  
首页顶部导航栏 → **AI Video** 下拉菜单。

**实现要求**

- 在下拉菜单的第一位新增 **AI Movie**，点击后进入 AI Movie 功能页。
- 菜单项沿用现有下拉菜单样式。

**验收标准**

- 打开首页 **AI Video** 下拉菜单，从上到下依次显示 **AI Movie**、**Image to Video**、**Text to Video**。
- 点击 **AI Movie** 可进入对应的功能页。

## 03｜首页顶部导航新增 Face Swap

**修改位置**  
首页顶部导航栏，紧邻 **AI Image** 右侧。

**实现要求**

- 在 **AI Image** 右侧新增独立的一级导航项 **Face Swap**。
- 点击 **Face Swap** 进入对应的换脸功能页。导航项沿用现有顶栏样式。

**验收标准**

- 首页顶栏中，**Face Swap** 紧接在 **AI Image** 右侧，直接显示在顶栏。
- 点击 **Face Swap** 可进入对应的功能页。

## 04｜首页 CTA 对齐 Vidou 的样式和动画

**修改位置**  
首页的 **Ready to Get Started?** CTA 模块。参考 [Vidou 首页](https://vidou.ai/) 的同名模块。

**实现要求**

- 按 Vidou 还原整个模块，包括黑色背景、底部绿色光晕、内容布局、字体和间距，以及绿色圆角 **Start Free Now** 按钮。
- 沿用参考模块的标题、说明文案和按钮文案。说明文案为 “Experience AI image-to-video generation now and bring your creativity to life.”
- 对照 Vidou 实际页面复现该模块的动画及交互效果，包括实际发生的变化、触发条件、时长、缓动和循环行为。若项目中可以复用 Vidou 的原组件或动画样式，优先复用。

**验收标准**

- 在相同的桌面和移动端视口下，新站 CTA 的文案、静态布局、配色和视觉细节与 Vidou 对应模块一致。
- 对两个页面执行相同的触发操作，确认动画的变化过程、节奏及播放行为一致。

## 05｜首页页脚 Product 栏新增 AI Movie 和 Face Swap

**修改位置**  
首页页脚 → **Product** 链接列表。

**实现要求**

- 将 **AI Movie** 添加到列表首位，将 **Face Swap** 添加到列表末位。
- 两个链接分别指向对应的功能页，复用首页顶部导航中的相同链接目标。

**验收标准**

- **Product** 栏从上到下依次显示 **AI Movie**、**Image to Video**、**Text to Video**、**Text to Image**、**Image Editor**、**Face Swap**。
- 点击新增的两项链接，可分别进入对应的功能页。

## 06｜About 页面新增 AI Movie 和 Face Swap 卡片

**修改位置**  
About 页面的 **Tools in the Vidou workspace** 区块。

**实现要求**

- 在现有四张工具卡片之后新增 **AI Movie** 和 **Face Swap**。复用现有卡片的图标、标题、说明文字布局及响应式网格样式，为两个功能分别配上对应的图标。
- **AI Movie** 说明文案建议为 “Create reusable characters, generate clips with consistent characters, and stitch them into a movie.”
- **Face Swap** 说明文案建议为 “Replace a face with one from a reference image.”
- 将区块引言中的 “four tools” 改为 “six tools”。

**验收标准**

- 工具区共显示六张卡片，桌面端新增两张卡片组成第三行，移动端沿用现有卡片的响应式布局。
- 新卡片标题分别为 **AI Movie** 和 **Face Swap**，引言中的工具数量与卡片数量一致。

## 07｜Blog 页顶部导航与首页一致

**修改位置**  
[Blog 列表页](http://155.138.214.216:8090/blog/)的顶部导航栏。

**实现要求**

- Blog 页复用首页顶部导航组件，保持菜单内容、排列顺序、样式、链接目标和下拉交互一致。
- 同步应用第 02 项和第 03 项。**AI Movie** 位于 **AI Video** 下拉菜单首位，**Face Swap** 作为独立入口紧邻 **AI Image** 右侧。

**验收标准**

- 在相同视口下分别打开首页和 `/blog/`，核对导航布局、菜单顺序、下拉内容和交互一致。
- 在 Blog 页点击导航项，确认进入与首页相同的对应页面。

## 08｜顶部导航将 Pro Version 更名为 Premium Tools

**修改位置**  
首页及其他使用同一顶部导航的页面，位于 **Pricing** 右侧的绿色按钮。

**实现要求**

- 将按钮文案从 **Pro Version** 改为 **Premium Tools**，明确这是高级付费功能的入口。
- 沿用现有按钮样式和高级功能入口的链接目标。第 01 项提到的 **Pro Version** 按钮即此按钮。

**验收标准**

- 首页和 Blog 页的顶部导航均显示 **Premium Tools**。
- 点击 **Premium Tools** 可进入现有的高级付费功能页面。

## 09｜降低高级工具工作区顶部栏高度

**修改位置**  
高级工具（**Premium Tools**）工作区的顶部栏，即截图红框内显示当前功能标题（示例为 **Image to Video**）和右侧账户菜单的区域。

**实现要求**

- 降低顶部栏的整体高度，减少上下留白，并让功能标题和账户菜单在栏内垂直居中。
- 同步调整主内容区因顶部栏预留的顶部间距，使生成表单和 **My Creations** 等内容整体上移，为首屏腾出更多空间。
- 在共用该顶部栏的高级工具页面统一应用这项调整。

**验收标准**

- 在同一视口下打开修改前后的 **Image to Video** 工作区，顶部栏可见高度下降，生成表单和 **My Creations** 的顶部位置上移，首屏能看到更多内容。
- 功能标题和账户菜单完整显示，账户下拉菜单可正常打开。

## 10｜图生视频描述输入框新增写作指导

**修改位置**  
**Image to Video** 功能页的 **Your description** 输入框右上角，对应截图红框内的位置。

**实现要求**

- 在标记位置增加指导按钮，英文按钮文案为 **Guide**。为按钮留出空间，避免遮挡用户输入的文字。
- 点击按钮打开弹窗，展示如何编写 **Your description** 的指导。弹窗可关闭，打开和关闭时保留用户已输入的内容。

**弹窗英文文案**

**How to Write Your Description**

1. Just describe the video you want to create in your own words. Include as much detail as you can, and we'll turn your description into a professional prompt.
2. To refer to a specific image you've uploaded, click its `@img` tag above the description box. For example, `@img1 smiles at @img2.`
3. To make a character speak, use this format: `@img1 says: 'Hello.'`
4. Generate a preview first. If it doesn't look the way you want, try rephrasing your description or adding more detail, then generate another preview.

**验收标准**

- **Guide** 按钮显示在输入框右上角，点击可打开指导弹窗，显示上述四条英文指导。
- 关闭弹窗后，用户可以继续编辑原有描述。
