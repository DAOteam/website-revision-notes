# 新站修改意见

审查站点：[新站](http://155.138.214.216:8090/)

## 35｜将 AI Movie 电影编辑页的 PC 导航与移动端对齐

**状态：PC 端待修改。**

**修改范围**

AI Movie 电影编辑页内，站点顶栏下方的电影导航栏。PC 端采用移动端的布局与交互。

- 左侧保留 **All movies**。导航栏中间仅显示电影名，水平和垂直居中，长名称显示省略号。
- 右侧使用竖向三点菜单，第一项为 **Movie Info**，第二项为红色 **Delete**，沿用现有删除流程。
- **Movie Info** 弹窗显示名称、分辨率和宽高比。无生成结果时三项均可编辑。生成任何 Clip 结果后（含低清预览），仅名称可编辑，分辨率和宽高比只读。

**待验收**

- PC 端核对布局、菜单和弹窗与移动端一致。

## 47｜调整移动端积分记录的卡片布局

**状态：待修改。**

**现象**

移动端 **Credits History** 弹窗内，积分、任务说明和时间并排显示，任务说明被挤成多行，卡片过高。

**预期与验收**

- 改为两行布局。第一行左侧显示加粗的积分变动，右侧显示时间。第二行使用卡片内的全部可用宽度，显示任务名称和详情，例如 **AI Movie HD · 720p · 6s** 或 **Image to Video · Task 416385**。
- 在手机窄屏下检查扣费和退款记录。任务说明可自然换行，积分、时间和详情完整可见，彼此不重叠，弹窗无横向滚动。

## 48｜修复首页移动端菜单滚动并上移快捷入口

**状态：待修改。**

**现象**

首页右上角菜单展开后无法上下滚动，矮屏上看不到底部菜单项。当前底部绿色按钮显示 **Get Started Free**，文案与 PC 首页顶部的对应入口不一致。

**预期与验收**

- 菜单内容区适配手机可视高度，内容超出时可在菜单内上下滑动，确保所有菜单项可访问。
- 将原底部绿色按钮移到菜单内容区最上方，在 **AI VIDEO** 分组前独占一行。文案以 PC 端对应按钮为准（**Premium Tools**），点击后进入同一目标页面。
- 在手机窄屏和矮屏上展开菜单，确认顶部按钮独立显示且可点击，向下滑动可访问 **Pricing** 等底部菜单项。

## 49｜修复窄屏下作品卡片内容错位

**状态：待修改。**

**现象**

图生视频页的 **My Creations** 在较窄的手机屏幕上，作品名称被截断，状态标签和剩余时间被挤在同一行，导致剩余时间折断或被裁切。

**预期与验收**

- 作品名称可根据可用宽度自然换行，下载按钮保持完整可见且可点击。
- 状态标签和剩余时间在空间足够时同排展示。空间不足时，把剩余时间整体移到下一行左对齐，例如 **7d left** 作为一个整体显示。卡片高度应随内容调整。
- 在窄屏双列布局下检查卡片，确认标题、下载按钮、状态和剩余时间能完整显示，彼此不重叠，卡片无横向溢出。

## 50｜在图生视频和 AI Movie 的时长滑块下方加入提示

**状态：待修改。**

**修改范围**

**Image to Video** 和 **AI Movie** 的 Clip 编辑页。将英文提示放在 **Duration** 滑块及刻度下方，作为常驻辅助文字。

**英文文案**

> Match the duration to the action. Keep simple actions short. If you give them too much time, they can look like slow motion.

**验收标准**

- 两处时长设置均显示同一段文案。桌面端和移动端无需点击即可看到提示，窄屏下文字可自然换行。

## 51｜为 AI Movie 每个 Clip 的描述区添加 Guide 按钮

**状态：待修改。**

- 在每个 Clip 的 **Your description** 输入区右上角添加 **Guide** 按钮，沿用图生视频的入口和弹窗样式。
- 点击打开适用于 AI Movie 的描述指南。说明如何用自然语言描述当前 Clip 的动作和对白、如何用 `@名称` 引用参考图，以及如何先看预览再调整描述。示例使用 AI Movie 的引用方式。
- 在桌面端和移动端切换不同 Clip，确认每个 Clip 都能打开和关闭指南，原有输入内容保留。

## 52｜调整 AI Movie 的 Clip Guide 条目顺序

**状态：待修改。**

将第 51 项的 **Guide** 弹窗 **How to Write Your Description** 按原第 2、3、1、4 条的顺序排列，并重新编号为 1–4。沿用现有英文文案，显示顺序如下。

1. 用自己的话描述当前 Clip 的动作，并说明如何点击名称插入 `@` 引用。
2. 说明如何为角色编写对白，保留现有对白示例。
3. 说明如何用参考图保持角色、场景和道具一致。英文说明及示例如下，示例另起一行，放在说明下方。

   > To keep a character, location, or prop consistent across clips, you must mention it in the description for each clip where it appears. Use its reference image name with `@`, such as `@Maya`, `@Cafe`, or `@RedSuitcase`.
   >
   > **Example**  
   > `@Maya walks into @Cafe carrying @RedSuitcase.`
4. 先预览 Clip，按需调整描述并重新预览，满意后生成 HD。

**验收标准**

- 在桌面端和移动端打开任一 Clip 的 **Guide**，确认条目按上述顺序连续编号为 1–4，第 3 条的英文示例仍显示在该条说明下方，且保留三个 `@` 引用。

## 54｜调整 AI Movie 参考图区域的声音说明

**状态：待修改。**

- 将 **How voices work** 从 **Reference Images** 区域底部移到上方 **Characters**（参考角色）区的正下方，放在 **Scenes** 前。保留现有展开和收起交互，在标题 **How voices work** 前加黄色圆形信息图标（ⓘ）。
- 缩小黄色圆形信息图标，使其与标题文字大小协调。图标、标题文字和左侧展开箭头在同一行垂直居中对齐，图标与文字之间保留适当间距。桌面端和移动端均检查展开与收起时的对齐效果。
- 将当前关于两个女性在同一个 Clip 说话的说明替换为以下文案：

  > Use no more than one speaker with a reference voice per gender in each clip. If two characters of the same gender both speak and both have reference voices, one of their reference voices may be ignored. Split their dialogue into two clips and have one character speak in each.

- 删除整条旧说明：“Within one gender, voices are handed out in speaking order — set it under the prompt.” 保留音色和录音时长、文件大小的说明。

## 55｜为图生视频作品详情的 Task ID 添加复制按钮

**状态：待修改。**

- 在图生视频的作品详情弹窗中，在 **Task ID** 号码右侧添加复制按钮，按钮的无障碍名称为 **Copy task ID**。
- 点击后将当前任务的 ID 号码复制到剪贴板。例如显示 `Task ID: 416385` 时，粘贴结果为 `416385`。
- 复制成功后短暂显示 **Copied**。桌面端和移动端均可使用。

## 56｜统一全站功能页选项的选中样式

**状态：待修改。**

- 以 **AI Movie 设置弹窗**中的 **Aspect ratio** 和 **Resolution** 为样式基准。全站功能页面的可选参数按钮统一采用该选中效果，覆盖图生视频的分辨率、宽高比及其他功能页的同类选项。
- 选中项使用绿色描边、深绿色底和浅色文字。有图标时沿用参考样式的绿色图标。未选中项使用深灰底、灰色描边和灰色文字。图生视频切换后出现的灰底黑字应一并修复。
- 桌面端点击、悬停和移开鼠标，以及移动端点按后，选中样式均与当前值一致。切换选项后，新项立即高亮，原项恢复未选中样式。
- 桌面端和移动端均需核对全站功能页的参数选项。图生视频需额外验证预览生成前切换宽高比和分辨率，以及预览生成后切换 **720p / 1080p**。

## 57｜为移动端 AI Movie 的整片播放入口加上白色选中标记

**状态：待修改。适用范围：仅移动端。**

- 在移动端点击 AI Movie 左侧栏的播放按钮进入 **Whole movie** 时，在按钮左侧显示与选中 **Clip** 相同的白色竖条，保留按钮现有的绿色样式。
- 只在当前视图对应的入口显示白色竖条。进入 **Whole movie** 后移除 Clip 左侧的白条，切回某个 Clip 时将白条移回该 Clip。
- 在移动端来回切换 Clip 与 **Whole movie**，确认白条始终跟随当前视图。

## 58｜视频换脸在打开选脸弹窗后检测人脸

**状态：待修改。**

- 视频换脸的源视频上传完成后，等待用户点击 **Choose the face**。
- 点击后立即打开选脸弹窗，再开始检测当前源视频中的人脸。检测中的 **Finding the faces in your media…** 提示显示在弹窗内，结果返回后在弹窗内显示可选人脸。
- 验收时先上传视频并停留在表单，确认未发起检测。点击 **Choose the face** 后，确认弹窗先出现，并在其中显示检测进度和结果。

## 59｜在 AI Movie 作品列表显示保留期限和剩余时间

**状态：待修改。**

- 在 AI Movie 的 **YOUR MOVIES** 标题右侧加上提示 **Movies are kept for 3 months.** 窄屏空间不足时，提示可换到标题下方。
- 每张作品卡片的底部显示距离该作品到期的剩余时间，沿用图生视频 **My Creations** 的样式和格式，例如 **85d left**。用剩余时间替换卡片右下角目前显示的相对时间或日期。
- 倒计时以该作品的实际到期时间为准。桌面端和移动端均需确认提示可见、卡片倒计时完整显示。

## 60｜统一首页免费功能模块和等待页的 Pro 权益文案

**状态：待修改。**

更新首页免费功能模块的 **WANT BETTER RESULTS?** 卡片和免费任务等待页的 **Waiting too long? Go Pro** 卡片。

| 权益 | 首页免费功能模块 | 等待页 |
|---|---|---|
| 分辨率 | **1080p HD** resolution (vs low resolution on the free plan) | **1080p**，副文案为 **Low resolution on the free plan** |
| 音频 | **Audio generation** — synced character dialogue and sound effects (silent on free) | **Audio**，副文案为 **Synced character dialogue and sound effects** |
| 工具 | **All AI tools** — AI Movie, video, image, editing, Face Swap | **All AI tools**，副文案为 **AI Movie, video, image, editing, Face Swap** |

## 61｜允许移除图片编辑页已上传的图片

**状态：待修改。**

- 在图片编辑页 **Set up your edit** 区域，上传图片后，在预览右上角显示 × 按钮，无障碍名称为 **Remove image**。桌面端和移动端均可直接点击。
- 点击后清除当前图片和预览，恢复上传入口。保留已输入的编辑描述，用户可继续上传同一张或另一张图片。
- 验收时确认移除后不会用旧图提交任务，重新选图后使用新选中的图片。
