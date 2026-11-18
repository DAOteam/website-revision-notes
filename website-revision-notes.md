# 新站修改意见

审查站点：[新站](http://155.138.214.216:8090/)

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

## 62｜在 AI Movie 批量生成高清片段

**状态：待修改。**

**入口和确认**

- 在 **Whole movie → Preview** 的播放器下方提供 **Generate All Clips in HD**，旁边显示可生成的片段数和总积分，例如 **3 clips ready for HD · 120 credits**。有可生成片段时显示入口。批量范围为已有低清预览且尚无 HD 的 Clip，已有 HD 的片段直接保留，尚无预览的片段跳过。单个 Clip 页保留 **Generate Clip in HD**。
- 点击后打开确认框，列出本次生成的 Clip、生成顺序、电影设定的分辨率、总积分，以及已有 HD 或缺少预览而跳过的片段。示例标题 **Generate 3 clips in HD?**，确认按钮 **Generate 3 Clips · 120 credits**。积分沿用单段计价并合计，余额不足时显示缺少的积分，余额足够后方可提交。

**生成进度**

- 用户确认一次，系统按影片中的 Clip 顺序逐段生成 HD。同一批次每次处理一个片段。整片页在原入口处显示已完成数、当前片段和下一片段，例如 **Generating HD · 1 of 3 complete**、**Clip 4 is generating. Clip 5 is next.**。
- Clip 列表同步显示 **Queued for HD**、**Generating HD**、**HD ready**。已排队和生成中的片段在单段页面显示相应状态，防止重复提交。用户可继续看低清预览。离开或刷新后，任务继续运行，再打开时恢复进度。

**失败和完成**

- 某段失败且后续片段依赖它的 HD 结果时，暂停依赖的后续生成，标明失败段并提供 **Retry Clip 4** 之类的对应操作。该段重试成功后自动继续。后续片段可独立生成时，继续处理其余片段，最后汇总失败片段并提供 **Retry Failed Clips**。两种情况下均保留已完成的 HD。
- 本批完成但全片仍有片段缺少预览时，显示实际完成数（例如 **3 clips generated in HD**）并指出仍需预览的片段。全片每个 Clip 都已有 HD 时，才显示 **All clips are ready in HD**，并提供 **Watch Full Movie in HD**，沿用整片的 HD 播放和导出流程。

**验收**

- 用同时包含已有 HD、仅有低清预览和无预览的电影，核对确认范围、积分和逐段生成顺序。验收积分不足、重复提交、刷新恢复、失败重试以及全片 HD 就绪后的切换入口。

## 63｜移除 AI Movie 合并视频时的服务端切换提示

**状态：待修改。**

- 在 **Whole movie → Export as one file** 中，浏览器合并失败并自动切换到服务端合并时，移除卡片下方的提示 **Couldn’t join the clips in this browser — joining them on our server instead.**
- 如果服务端合并期间还会另行提示「无法使用浏览器合并，正在使用我们的服务器合并」，一并移除这条提示。Preview 和 HD 的整片导出均适用。
- 服务端继续自动合并，卡片保留 **Joining…** 和用时。合并成功后保留现有下载入口，服务端也合并失败时仍显示最终错误。

## 64｜移除 AI Movie 的 Check the seam 按钮

**状态：待修改。**

- 在 AI Movie 单个 Clip 编辑页，移除视频播放器下方、**Your description** 上方右侧的 **Check the seam** 按钮。移除按钮占用的空间，保留播放器和片段预览。
- 在桌面端和移动端打开已有预览的后续片段，确认按钮已移除，视频仍可正常播放。

## 66｜重新生成中间 Clip 的 Preview 前要求确认

**状态：待修改。**

- 在 AI Movie 的 Clip 编辑页，用户点击重新生成已有 Preview 时，检查当前中间 Clip 之后的所有片段。只要任一后续 Clip 已生成 Preview 或 HD，即使中间隔着未生成的片段，也必须先弹出警告。
- 弹窗标题为 **Regenerate this preview?**，正文为 **The new preview may no longer match the clips before and after it.** 如果当前 Clip 已有 HD，再显示 **You’ll lose the existing HD video for this clip.**
- **I understand and agree** 复选框每次打开都默认不勾选。**Regenerate Preview** 按钮默认灰色且禁用，勾选后才可点击，取消勾选后立即恢复禁用。关闭弹窗或点击 **Cancel** 时，保留当前 Preview 和 HD，不提交生成任务。
- 用户确认后才启动重生成。新 Preview 生成成功后替换旧 Preview，并移除当前 Clip 已有的 HD。生成失败时保留旧 Preview 和 HD。
- 重生成中间 Clip 只更新当前 Clip。后续每个 Clip 已生成的 Preview 和 HD 都必须保留。验收时在当前 Clip 重生成成功后，逐个打开已有结果的后续 Clip，确认原有 Preview 和 HD 仍可播放。
- 验收覆盖后续只有 Preview、只有 HD、隔段已有结果、后续均无结果，以及当前 Clip 有无 HD 的情况。确认有后续结果时无法绕过勾选直接提交。

## 67｜移动端顶栏居中显示当前页面名称

**状态：待修改。适用范围：移动端功能页及 Pricing 页。**

- 移除顶栏中的 **Vidou.ai** 网站名，在顶栏正中显示当前页面名称。图片编辑页显示 **Image Edit**，图生视频页显示 **Image to Video**，电影页显示 **AI Movie**，定价页显示 **Pricing**。切换页面时，顶栏标题随之更新。
- 左侧保留菜单按钮，右侧保留账户入口。标题相对于整个顶栏水平居中、垂直对齐，在登录与未登录状态下均不被两侧按钮挤偏或遮挡。
- 用手机窄屏在多个功能页与 **Pricing** 页之间切换，确认标题更新且始终居中，两侧入口仍可点击。
