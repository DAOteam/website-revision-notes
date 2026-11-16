# 新站修改意见

审查站点：[新站](http://155.138.214.216:8090/)  
颜色参考：[Vidou](https://vidou.ai/)

## 验收进度

22 项修改中，**21 项已完成，仅第 18 项尚未实现**。

| 状态 | 项目 |
| --- | --- |
| 已完成 | 01–17、19–22 |
| 尚未实现 | 18｜图生视频单图任务使用新的系统提示词和图片输入 |

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

## 11｜将 7 天保留提示移到 My Creations 标题右侧

**修改位置**  
作品列表顶部，当前位于 **My Creations** 标题下方的提示横条。

**实现要求**

- 将提示移到 **My Creations** 标题右侧，与标题同一行。移除标题下方原有的整行提示横条。
- 将英文提示缩短为 **Tasks kept for 7 days**。

**验收标准**

- 标题右侧显示 **Tasks kept for 7 days**，标题下方直接显示作品列表。
- 在窄屏下检查标题和提示，确保文字完整可读，布局无重叠。

## 12｜移除作品卡片上的工具标签并统一标题大小写

**修改位置**

**My Creations** 作品列表的卡片，涉及预览缩略图及其下方的工具标题。

**实现要求**

- 移除所有作品卡片缩略图左上角叠加的工具名称标签，例如截图红框中的 **vidou AI image to video generator** 和 **vidou AI video generator**。
- 将卡片下方工具标题中的 **To** 改为小写 **to**，与工具导航命名一致。截图示例为 **Image to Video** 和 **Text to Video**。同样的规则适用于其他包含 **to** 的工具标题，例如 **Text to Image**。

**验收标准**

- 作品预览缩略图上不再显示工具名称标签。
- 图生视频和文生视频卡片的标题分别显示为 **Image to Video** 和 **Text to Video**。

## 13｜作品弹窗中的视频改为手动播放

**修改位置**

**My Creations** 作品列表中，点击视频任务后打开的作品弹窗。

**实现要求**

- 打开视频作品弹窗时，播放器默认处于暂停状态。用户点击视频或播放按钮一次后，才开始播放。
- 每次打开弹窗（包括关闭后重新打开同一作品）都应用这一规则。

**验收标准**

- 打开任意可播放的视频作品，等待媒体加载完成，确认画面保持暂停且没有播放声音。
- 点击播放控件一次，视频正常开始播放。关闭弹窗并重新打开，视频仍等待用户手动播放。

## 14｜调整图生视频预览按钮并增加帮助提示

**修改位置**

**Image to Video** 生成表单底部的操作区，即 **Generate** 和预览按钮所在的位置。

**实现要求**

- 将右侧预览按钮文案改为 **Preview First· 10 credits**。
- 缩短左侧 **Generate** 按钮的宽度，为新版预览按钮和帮助图标留出空间。
- 在 **Preview First· 10 credits** 按钮紧邻右侧添加独立的 **?** 帮助按钮。点击问号只打开说明提示，预览仍由预览按钮触发。

**提示英文文案**

> Before generating your HD video, create a low-resolution preview. If the preview isn’t quite right, edit your video description and generate another preview. It’s the quickest, lowest-cost way to try different descriptions. Once you’re happy with the preview, generate the HD video.

**验收标准**

- **Generate** 按钮变窄，右侧依次显示完整的 **Preview First· 10 credits** 文案和 **?** 帮助按钮。
- 点击 **?** 显示上述英文提示，且不提交任务或扣除积分。

## 15｜修复图片换脸价格不随配对数量变化的问题

**修改位置**

**Face Swap** 的图片换脸模式。

**当前问题**

配置一对或多对人脸时，页面显示的积分价格相同。

**实现要求**

- 根据本次任务中已完成配置的有效人脸配对数计算总积分。新增或移除配对后，页面报价应即时更新。
- 核对任务提交时的后端计价与实际扣费，确保和页面显示的总积分一致。具体单价以产品定价配置为准。

**验收标准**

- 分别配置一对、两对及更多有效配对，确认所需积分按配对数量和定价规则变化。
- 移除一对后，确认报价相应更新。提交任务后，核对实际扣除的积分与提交前显示的报价一致。

## 16｜积分记录分别显示任务扣分和失败退分

**修改位置**

用户账户的积分记录，适用于产生积分扣减的任务。

**实现要求**

- 任务成功发起并扣除积分时，写入一条扣分记录，显示实际扣除的积分，例如 **−80 credits**。
- 任务失败并退还积分时，单独新增一条退分记录，显示实际退回的积分，例如 **+80 credits**，并标明退款原因是任务失败。英文原因文案建议为 **Task failed**。
- 扣分和退分记录关联同一个任务。重复处理同一个失败事件时，同一任务只退分并记录一次。

**验收标准**

- 发起一笔消耗 80 积分的任务后，积分记录立即显示 **−80 credits**。
- 若该任务失败，积分记录同时保留原扣分和新增的 **+80 credits**，退分记录明确标注 **Task failed**，余额恢复到扣分前的水平（期间无其他积分变动）。
- 任务成功时仅显示扣分记录。重复处理失败事件时，余额和退分记录均只更新一次。

## 17｜Pricing 页新增各功能的积分收费标准

**修改位置**

**Pricing** 页，三张积分套餐价格卡片的正下方。新增一个独立模块，英文标题建议为 **Credit Costs by Tool**。

**实现要求**

- 逐项列出当前开放功能的积分收费标准，包括 **Image to Video**、**Text to Video**、**Text to Image**、**Image Edit**、**Face Swap** 和 **AI Movie**。
- 每项明确标示实际积分费率和计费单位。若价格受分辨率、时长、人脸配对数量或其他设置影响，列出适用档位或计算规则。若预览和正式生成分开收费，分别说明。
- 收费标准以各功能实际生效的定价配置为准，并与功能页提交任务前显示的报价一致。

**验收标准**

- Pricing 页三张价格卡片下方可看到完整的收费标准模块，每个在用功能均可查到对应规则。
- 选择不同计费设置，并按照 Pricing 页列出的规则计算总价，结果与对应功能页显示的积分相符。

## 18｜图生视频单图任务使用新的系统提示词和图片输入

**状态：尚未实现。**

**修改位置**

**Image to Video** 根据用户描述生成专业视频提示词的步骤。

**实现要求**

- 当本次图生视频任务恰好上传 **1 张图片**时，使用新的单图系统提示词。零张或多张图片的任务沿用各自现有的处理流程。
- 调用生成专业提示词的大模型时，将用户上传的这张图片作为模型可读取的图像输入，与用户原始描述一起发送。
- **新的系统提示词正文待补充。**

**验收标准**

- 提交单图任务，确认生成提示词的请求使用新的单图系统提示词，并包含用户上传的实际图片和原始描述。
- 提交双图及三图任务，确认未进入单图分支。

## 19｜HD 图生视频任务提交后自动清空表单

**修改位置**

**Image to Video** 生成表单，适用于点击 **Generate** 提交 HD 视频任务的流程。

**实现要求**

- 服务端确认 HD 任务创建成功后，立即自动清空本次任务的所有输入，包括已上传的参考图片、描述文字及其他已填写字段，并将生成选项恢复为新任务的默认值。
- 新任务进入队列后，用户即可填写下一份表单。
- 点击 **Preview First** 生成预览，或 HD 任务提交失败时，保留表单输入，方便修改或重试。

**验收标准**

- 上传参考图片、输入描述并提交 HD 任务。任务创建成功后，任务使用提交时的完整输入，页面表单立即重置，可直接填写下一个任务。
- 分别测试预览生成和 HD 提交失败，确认原有图片、描述和选项仍可继续使用。

## 20｜更新 AI Movie 页的 SEO 标题和元描述

**修改位置**

**AI Movie** 页面 HTML 的 `<title>` 和 `<meta name="description">`。

**英文文案**

| 字段 | 文案 | 字符数 |
| --- | --- | --- |
| Title | AI Movie Maker for Consistent Characters \| Vidou | 48 |
| Meta description | Create a reusable character library, generate video clips with consistent characters, and stitch them into a movie with Vidou's AI Movie Maker. | 143 |

**验收标准**

- 打开 AI Movie 页面，检查最终 HTML 输出中的标题和元描述均与表格文案一致。
- 标题不超过 60 字符，元描述不超过 160 字符，空格和标点计入字符数。若站点自动附加品牌名，确保标题中只出现一次 **Vidou**。

## 21｜在 Terms of Service 中补充 Face Swap 使用条款

**修改位置**

站点的 **Terms of Service** 页面，以及 **Face Swap** 功能区勾选确认处的协议链接。

**当前问题**

Face Swap 功能区要求用户确认素材使用权和人物同意，并接受 Terms of Service。当前协议缺少对应的换脸使用条款。

**实现要求**

- 在 **Terms of Service** 中新增 **Face Swap** 小节，适用于图片和视频换脸。
- 将 Face Swap 勾选确认处的 **Terms of Service** 链接定位到该小节。页面提示、勾选文案和协议条款对素材使用权、肖像同意和禁止用途的说明应一致。

**协议英文文案**

### Face Swap

Face Swap is for entertainment only. You may upload and use photos or videos only if you have the rights and permissions to use them. Before using anyone else’s likeness in a face swap, you must obtain their consent to the intended use. If you plan to share the result, their consent must also cover that sharing.

You may not use Face Swap to create or share sexual, deceptive, or illegal content. Prohibited uses include impersonating someone to mislead others, creating false endorsements, and using a person’s likeness for fraud.

**验收标准**

- 从 Face Swap 功能区点击 **Terms of Service**，可直接查看 **Face Swap** 条款。
- 条款明确写明娱乐用途、上传素材使用权、使用他人肖像前须取得同意，以及禁止性内容、欺骗性内容和违法内容。

## 22｜所有协议页的顶部导航与首页一致

**修改范围**

站点现有的所有协议和政策页面，包括 **Terms of Service**、**Privacy Policy** 及其他同类页面。

**实现要求**

- 复用首页顶部导航组件，使菜单顺序、样式、链接目标、下拉交互及移动端导航与首页一致。
- 同步应用第 02、03 和 08 项。**AI Movie** 位于 **AI Video** 下拉菜单首位，**Face Swap** 作为独立入口紧邻 **AI Image** 右侧，付费工具入口显示为 **Premium Tools**。

**验收标准**

- 在相同桌面和移动端视口下打开首页及各协议页，核对顶部导航的布局、菜单内容和交互一致。
- 从协议页操作顶部导航，确认菜单可正常展开，各入口跳转至与首页相同的目标。Face Swap 页面链接到协议中对应条款的定位仍正常。
