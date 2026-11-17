# 新站修改意见

审查站点：[新站](http://155.138.214.216:8090/)

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

## 29｜补齐全站按钮的鼠标悬停反馈

**状态：尚未完成。**

**当前问题**

部分可点击按钮在鼠标移入时缺少可见的悬停效果，或光标仍是箭头、没有变成小手。

**实现要求**

- 检查全站可点击按钮，覆盖主要按钮、次要按钮、图标按钮和弹窗按钮，补齐缺失的 hover 样式。
- 可点击的按钮在整个点击区域（包括图标和文字上方）使用 `cursor: pointer`，检查共享按钮和自定义按钮。
- 沿用现有按钮视觉规范，通过背景、边框或文字颜色变化提供清晰反馈。鼠标移出后恢复原有状态。
- 禁用按钮保持禁用外观，选中按钮的选中样式在悬停时仍清晰可辨。

**验收标准**

- 在桌面端逐一检查主要页面和弹窗。鼠标移入可点击按钮时，光标变成小手，同时出现可见的悬停反馈。移出后恢复原样。
- 禁用按钮仍不可点击，悬停时不显示小手。选中状态与普通悬停状态可区分。

## 33｜功能页的介绍图文仅向未登录访客展示

**修改范围**

所有独立功能页，包括 **Image to Video**、**Text to Video**、**Text to Image**、**Image Edit**、**Face Swap** 和 **AI Movie**。仅调整工具操作区下方的介绍图文。

**实现要求**

- 未登录时，展示工具操作区下方的完整介绍内容，包括已有的图文、操作步骤、FAQ、相关工具和底部 CTA。公开 HTML 中仍可读取这些介绍内容。
- 登录后，隐藏整个介绍区，并收起该区域占用的空间。工具操作区、任务结果、**My Creations** 和全站公共页脚按原有逻辑显示。
- 在当前页登录或退出后，介绍区按最新登录状态切换。

**验收标准**

- 分别以访客和已登录用户打开六个功能页，确认介绍区只在访客状态下显示。
- 在功能页内登录后确认介绍区立即收起，退出后恢复。两种状态下均可看到工具操作区。

## 34｜AI Movie 移动端卡片改为上下排列

- 在移动端将 AI Movie 页面的两张入口卡片从双列改为单列。上方显示 **Create a movie**，下方显示 **Character library**。
- 两张卡片分别占满内容区的可用宽度，沿用现有间距规范。桌面端沿用双列布局。
- 验收时，在手机宽度下确认卡片按上述顺序展示，文字、头像和入口完整可见，页面无横向滚动。

## 35｜调整 AI Movie 电影编辑页的移动端导航

**修改位置**

AI Movie 电影编辑页内，站点顶栏下方的电影导航栏。

**实现要求**

- 左侧保留 **All movies** 返回入口。中间只显示当前电影名称，相对于整个导航栏水平和垂直居中。长名称在两侧控件之间截断并显示省略号。
- 右侧将原有的 **Delete** 按钮改为竖向三点按钮（⋮）。点击展开下拉菜单，第一项为 **Movie Info**，第二项为红色的 **Delete**，沿用原有删除流程。
- 点击 **Movie Info** 打开弹窗，显示当前电影的名称、分辨率和宽高比。还没有生成任何 Clip 时，三项均可编辑并保存。只要已有任何一个 Clip 的生成结果，即使只有预览，便只允许编辑并保存名称，分辨率和宽高比显示为只读。
- 仅创建空 Clip 或填写内容后仍可编辑三项。保存时校验最新状态，确保已有生成结果的电影无法更新分辨率和宽高比。

**验收标准**

- 在手机宽度下检查电影名居中、长名称显示省略号、左右控件可操作，并确认菜单项顺序及删除项颜色。
- 分别检查无生成结果（含只有空 Clip）、仅生成过预览、已有 HD 结果三种状态。前一种状态三项均可保存，后两种状态只能保存名称。

## 36｜在 AI Movie 移动端的描述上方独立显示参考图

**修改位置**

仅调整 AI Movie 的移动端 Clip 编辑页。将 **Reference Images** 放在预览画面下方、**Your description** 上方。桌面端继续使用现有布局和交互。

**实现要求**

- 使用 **Reference Images** 作为独立区块标题。没有参考图时，在标题下显示 **＋ Add reference images** 按钮。有参考图时，在标题右侧始终显示 **Manage** 按钮。
- 两个按钮都打开同一个现有的底部弹窗。弹窗内按 **Characters / Scenes / Props** 分组，可继续添加或移除参考图。
- 添加后，沿用编辑页现有的绿色 `@名称` 标签样式。按类别分组，每组标签前显示分类名称，例如 **People** `@elon`、**Scenes** `@Scene1`、**Props** `@Prop1`。同一类别有多张图时，分类名称只显示一次。
- 点击 `@名称` 标签，在描述输入框的光标处插入引用。窄屏下，标签可换行。

**验收标准**

- 未添加时，点击 **＋ Add reference images** 打开弹窗，分别添加角色、场景和道具。返回后确认标题右侧显示 **Manage**，每组标签前都有分类名称，点击标签可将引用插入描述。
- 点击 **Manage** 重新打开同一个弹窗，确认可继续添加或移除图片。移除全部参考图后，编辑页恢复 **＋ Add reference images** 入口。

## 37｜移动端 Clip 提交预览后自动滚动到顶部

**修改范围**

AI Movie 的移动端 Clip 编辑页。

**实现要求**

- 用户点击 **Preview** 且预览任务提交成功后，自动将当前 Clip 编辑页滚动到顶部，让用户立即看到预览区的任务状态，确认预览已发起并正在等待生成。
- 提交失败时保留当前滚动位置，沿用现有错误提示。

**验收标准**

- 在手机上滚动到 **Preview** 按钮并提交任务，确认页面自动回到顶部，无须手动滚动即可看到预览任务的等待状态。

## 38｜修复移动端 Clip 视频缺少播放按钮

**修改范围**

AI Movie 的移动端 Clip 编辑页，包含已生成的预览视频和 HD 视频。

**实现要求**

- 视频可播放时，在视频画面中央显示清晰可点击的播放按钮。点击后播放当前 Clip 视频，暂停后重新显示播放按钮。
- 播放按钮须适配移动端视频容器，确保窄屏上完整可见。

**验收标准**

- 在手机上分别打开已生成的预览视频和 HD 视频，确认播放前可看到播放按钮，点击后正常播放，暂停后可再次点击播放。

## 39｜移动端 Clip 生成预览和 HD 后纵向排列操作按钮

**修改范围**

AI Movie 的移动端 Clip 编辑页，预览视频或 HD 视频生成成功后显示的操作区。

**实现要求**

| Clip 状态 | 上方按钮 | 下方按钮 |
| --- | --- | --- |
| 预览视频已生成 | **Generate Clip in HD** | **Preview Clip again** |
| HD 视频已生成 | **Add Clip →** | **Preview Clip again** |

- 两种状态均使用单列布局，按钮等宽并撑满操作区，留出适当的纵向间距。
- 沿用按钮现有功能和文案。允许文案自然换行，按钮高度随内容调整，完整显示分辨率和积分。

**验收标准**

- 在手机窄屏上分别生成预览视频和 HD 视频，确认两种状态下的按钮均按表中顺序排列，文案完整、互不重叠，且均可点击。

## 40｜AI Movie 的 Clip 生成 HD 时省略低清预览视频的尾帧

**实现要求**

- 已有低清预览的 Clip 发起 HD 生成任务时，发送给 HD 生成工作流的请求省略该 Clip 的低清预览视频尾帧。
- 其他输入沿用现有流程。此项适用于桌面端和移动端的 Clip HD 生成流程。

**验收标准**

- 生成 Clip 的低清预览后发起 HD 任务，检查发送给 HD 工作流的实际请求，确认其中省略了该低清预览视频的尾帧，且 HD 视频可正常生成。

## 41｜AI Movie 整片播放页仅支持 HD 播放和导出

**修改范围**

AI Movie 的 **Whole movie** 整片播放页及其导出流程。

**实现要求**

- 移除 **HD / Preview** 切换控件。整片播放仅使用 Clip 的 HD 视频。
- 整片导出仅使用 HD 视频。仅生成低清预览的 Clip 不得作为播放或导出的素材。没有可用的 HD 视频时，提示用户先生成 HD Clip。
- 单个 Clip 编辑页仍可播放该 Clip 的低清预览。

**验收标准**

- 使用同时包含已生成 HD 的 Clip 和仅生成低清预览的 Clip 的电影，确认整片页没有 **Preview** 切换入口，播放和导出均不使用低清预览素材。
- 使用只有低清预览的电影，确认整片页提示先生成 HD，且无法播放或导出低清预览。

## 42｜修复 AI Movie 移动端页面的横向溢出

**现象**

在手机上打开 AI Movie 页面时，整页可以左右滑动。

**实现要求**

- 找出超出可用宽度的元素，让内容、控件和弹窗适配手机屏幕。长文案可换行，避免裁切文字或按钮。
- 整个页面仅沿纵向滚动。

**验收标准**

- 在不同手机宽度下打开 AI Movie 页面，检查主要界面和弹窗。左右滑动时页面不横移，文字及操作按钮完整可见。

## 43｜移动端整片播放页首屏显示导出按钮

**修改范围**

AI Movie 移动端的 **Whole movie** HD 播放页。目前播放器占用较多纵向空间，需向下滑动才能看到导出视频按钮。

**实现要求**

- 根据手机可视区高度缩小播放器显示区域，为下方导出视频按钮留出空间，使按钮在首屏完整可见并可点击。
- 缩小时保持视频原有宽高比，完整显示画面和播放控件。优先检查占用纵向空间较多的 9:16 视频。

**验收标准**

- 在不同手机视口高度下打开可导出的 HD 电影，尤其是 9:16 竖屏电影，确认进入页面后无需下滑即可看到并点击导出按钮。

## 44｜丰富 AI Movie 和 Face Swap 功能页的介绍图文

**修改范围**

两个功能页的工具操作区下方。沿用第 33 项的展示规则，未登录访客可见完整内容，公开 HTML 可读取主要文字。以下英文作为页面文案底稿。

### AI Movie

围绕 **AI movie maker** 和 **AI short film maker** 组织内容，重点介绍用户如何复用角色并逐段制作短片。

| 模块 | 英文标题与正文 | 配图 |
| --- | --- | --- |
| 产品介绍 | **Make a short film with consistent characters.** Build your film one clip at a time. Reuse characters from your library and export your HD clips as one movie. | 用同一原创角色在两段不同场景中的画面，搭配整片播放界面。 |
| 角色与参考图 | **Reuse characters, scenes, and props.** Add recurring characters from your library. Use reference images to show what a location or prop should look like, and mention it by name in your clip description. | 展示实际的 Reference Images 分类，以及通过 @名称引用素材的操作。 |
| 制作流程 | **Preview each clip before generating it in HD.** Describe what happens in a clip, preview the result, and revise the description if needed. When you are happy with the preview, generate the clip in HD and move on to the next one. | 用同一个 Clip 展示描述、预览和 HD 结果。 |
| 整片播放与导出 | **Play and export your film in HD.** Open Whole movie to watch your HD clips in order and export them as a single video. | 展示整片播放与导出入口，以第 41 项的 HD 流程为准。 |

**FAQ 文案**

- **Can I use the same character in multiple clips?** Yes. Add the character from your library and reference them by name in each clip where they appear.
- **What can I add as a reference image?** You can add characters, scenes, and props. Reference them by name when describing what happens in a clip.
- **Can I export a movie made from preview clips?** Movie export uses HD clips. Generate each clip you want to include in HD before exporting.

### Face Swap

围绕 **AI face swap**、**photo face swap** 和 **video face swap** 组织内容，分别说明两种任务的输入和操作。

| 模块 | 英文标题与正文 | 配图 |
| --- | --- | --- |
| 产品介绍 | **Swap faces in photos and videos.** Choose the photo or video you want to edit, then add a photo of the face you want to use. Select which face to replace and generate your result. | 用获得许可的示例素材，展示原图、替换人脸及处理结果。 |
| 图片换脸 | **Choose who to replace in a group photo.** Upload a group photo, then match each face you want to replace with its replacement. | 用多人合影展示实际的人脸配对界面，示例数量以当前功能为准。 |
| 视频换脸 | **Swap a face in a video.** Upload the video you want to edit and a clear photo of the replacement face. Use the video workflow to generate your result. | 用同一时刻的画面对比原片和结果，配合实际上传界面。 |
| 素材准备与使用要求 | **Use a clear photo and get consent.** A well-lit photo with an unobstructed face is a good starting point. Use only photos and videos you have the right to use, and get consent from anyone whose likeness you use. | 展示可用的参考图示例，并链接到 Terms of Service。 |

**FAQ 文案**

- **Can I swap faces in both photos and videos?** Yes. Choose the photo or video workflow based on the file you want to edit.
- **Can I replace more than one face in a photo?** Yes. In photo mode, match each face you want to replace with its replacement.
- **What kind of photo should I use for the replacement face?** Start with a sharp, well-lit photo where the face is clearly visible.
- **How many credits does a face swap cost?** See Pricing for current rates. 发布前核对图片和视频各自的计费规则，若补充具体数字，以实际上线价格为准。

**SEO 与 GEO 验收**

- 两个页面各自使用清晰的英文小标题，工具用途、输入、结果和限制用可见正文说明。FAQ 先直接回答问题，再交代适用条件。
- 用实际界面和前后对比展示流程。给图片添加描述具体画面信息的英文 alt 文本。关键操作和说明同步保留在 HTML 文本中。
- 在相关段落自然链接到 **Image to Video**、**Pricing** 或 **Terms of Service** 等对应页面。发布前逐条核对预览与 HD 的用途、换脸配对和计费文案。
- 参考 [Google Search Central 的 AI 搜索功能指南](https://developers.google.com/search/docs/appearance/ai-features)。
