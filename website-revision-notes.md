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

## 23｜更新 AI Movie 工作区的参考图和视频片段文案

**修改位置**

**AI Movie** 工作区的参考图区域及片段相关界面。

**实现要求**

- 将存放角色、场景和道具图片的区域标题 **Cast** 改为 **Reference Images**。
- 将指代视频片段的用户可见文案 **Segment** 和 **Segments** 统一改为 **Clip** 和 **Clips**。对应按钮文案按实际操作更新，例如 **Add Clip**、**Generate Clip**、**Preview Clip**。

**验收标准**

- AI Movie 工作区的参考图区域显示 **Reference Images**。
- 片段相关的标题、按钮及其他提示文案统一使用 **Clip** 或 **Clips**。

## 24｜更新 AI Movie 首屏文案和登录表单标签

**修改位置**

**AI Movie** 页的未登录首屏，以及从该页打开的登录表单。

| 位置 | 现有文案或问题 | 修改要求 |
| --- | --- | --- |
| 首屏标题 | Turn a story into a short film | **Make a movie with consistent characters** |
| 首屏说明 | Write a few sentences, pick your characters, and get a film made segment by segment — the same faces and voices from the first shot to the last. | **Create a cast you can reuse across clips, generate each clip, and stitch them together into a movie.** |
| 登录表单 | **Email** 和 **Password** 只显示为输入框的占位文字，输入后字段名消失。 | 为两个输入框分别添加常驻可见标签 **Email** 和 **Password**，并将标签与对应输入框关联。 |

**验收标准**

- 未登录时打开 AI Movie 页，首屏标题和说明与表格中的新文案一致。
- 打开登录表单，在两个字段输入内容后，**Email** 和 **Password** 标签仍清晰可见。

## 25｜修正图生视频和文生视频的 SEO 与分享描述

**修改位置**

图生视频页 `/image-to-video/` 和文生视频页 `/text-to-video/` 的 `meta description`、`og:description`（Open Graph）和 `twitter:description`（Twitter Card）。

**实现要求**

- 两页的正式视频输出支持 **720p 和 1080p**。将三个描述字段中的 **480p to 1080p** 统一改为 **720p or 1080p**，与页面正文和结构化数据一致。
- 保留各页现有 SEO 标题和描述中其余文案。

**验收标准**

- 上线前检查两个页面返回的 HTML，确认各自的三个描述字段均使用 **720p or 1080p**，并核对正文和结构化数据中的输出规格一致。

## 26｜所有独立功能页向访客完整展示工具操作区

**修改范围**

所有独立功能页，包括 **Image to Video**、**Text to Video**、**Text to Image**、**Image Edit**、**Face Swap** 和 **AI Movie**。

**实现要求**

- 未登录时，完整展示各功能的公共操作区域，包括表单、输入入口、设置选项和操作按钮。访客可以直接浏览工具界面，在尝试操作时进入登录流程。
- 未登录访客尝试输入、粘贴、上传或拖入素材、选择或调整参数，或点击提交、保存、预览和生成等操作时，立即打开现有登录弹窗。先拦截该操作，等登录成功后再允许使用功能。
- 单纯访问页面、滚动阅读及查看静态说明时，无需弹出登录窗口。

**验收标准**

- 在未登录状态下逐一访问六个功能页，确认工具操作区完整可见。
- 分别用鼠标和键盘尝试操作输入框、上传入口、参数控件和执行按钮，确认触发登录弹窗，且登录前没有实际上传、提交或执行操作。
- 关闭登录弹窗后仍可浏览完整界面。登录后可正常使用工具。

## 27｜调整功能页侧栏顺序并高亮当前页面

**修改位置**

功能页共用的左侧菜单。

**实现要求**

- 将 **AI Movie** 移到 **Image to Video** 的正下方。功能项从上到下依次为 **Image to Video → AI Movie → Text to Video → Image Edit → Text to Image → Face Swap**。**Pricing** 位于分隔线下方。
- 根据当前访问的页面显示对应菜单项的选中样式。选中态需明显区别于默认和悬停状态，对应链接标记为 `aria-current="page"`。

**验收标准**

- 打开功能页，确认 **AI Movie** 紧接在 **Image to Video** 下方。
- 通过点击侧栏、直接输入地址、刷新页面及使用浏览器前进或后退切换页面时，均只有当前页面对应的菜单项显示选中效果。验证范围包括 **Pricing**。

## 28｜重写 Face Swap 工具下方的英文图文内容

**修改位置**

`/face-swap/` 页工具模块下方、公共页脚上方的介绍区。复用 Image to Video 和 Image Edit 页已有的介绍区组件，包括三步流程卡片、图文模块、FAQ、相关工具和底部 CTA。下方为可直接上线的英文文案及配图要求。

### 页面标题和简介

**H1** — AI Face Swap for Photos, GIFs, and Videos

Replace one face or several in a photo, GIF, or video. Give each person a different face, or use the same face for everyone. For videos, select just the part you want to use and check the credit cost before you generate.

### How to Use Face Swap

1. **Upload your photo, GIF, or video**  
   Choose the file you want to edit. For a video, use the full clip or trim it to the part you want to swap. The selected clip must be at least 5 seconds long.
2. **Choose the faces to replace**  
   In **Specific Faces**, pair each face you want to change with a replacement photo. Keep the remaining faces as they are, or choose **Swap All Faces** to use the same replacement for everyone.
3. **Check the cost and generate**  
   Review the credit total before you start. Open the finished swap in **My Creations** to review or download it.

### Swap One Face or Several

In a group photo, you can replace one face and keep the others as they are. To use a different replacement for each person, add a separate face pair. **Swap All Faces** uses one replacement for everyone in the image or clip.

**配图要求** — 使用已获授权或合成的三人照片制作 Before / After 示例。仅替换中间一人，两侧人物、背景和构图保持一致。图上标注 **Original** 和 **One Face Swapped**。  
**Alt text** — Before and after a group photo face swap that replaces only the center person’s face.

### Swap a Face in Part of a Video

Use the trimmer to select the part of the video you want to edit. If the automatic selection misses someone, open the face slot in the pair, pause on a frame where the person is clearly visible, and select their outlined face.

**配图要求** — 使用实际工具界面或与现有界面一致的示意图，展示视频剪裁区间及用于选脸的清晰帧。沿用其他工具页图文模块的图片比例和排版。  
**Alt text** — Face Swap video trimmer with a selected clip and a face outlined in the preview.

### Choose a Clear Replacement Photo

- **Use a sharp, front-facing photo.** Keep the whole face in frame, with the eyes, nose, and mouth visible.
- **Match the angle and lighting.** Choose a replacement photo with a similar head angle and light direction.
- **Review the result.** For video, play through the clip and watch for changes around the face edges, especially when the person turns or passes behind something.

### Face Swap FAQ

- **Which files can I use?** Start with a JPEG, PNG, WebP, GIF, MP4, MOV, or WebM file. Use a JPEG, PNG, or WebP photo for each replacement face.
- **Can I replace multiple faces?** Yes. Add a face pair for each person you want to change, or use **Swap All Faces** to apply the same replacement to everyone.
- **What if the face I want isn’t detected?** Choose a clearer source image or, for a video, pause on a frame where the person’s full face is clearly visible and select their outlined face.
- **How much does a face swap cost?** The tool shows the credit total before you generate. The cost depends on the file type and the number of face pairs. For videos, the selected duration and source resolution also affect the total. See **Pricing** for the current rates.
- **What can I use Face Swap for?** Face Swap is for entertainment. Use media you have permission to use and get consent before using someone else’s likeness. See the **Face Swap** section of the **Terms of Service** for the full rules.

### Explore More AI Tools

- **Image to Video** — Animate a still image by describing how you want it to move.
- **Image Editor** — Describe a focused change to an image and specify what to keep.

### Ready to Swap Faces?

Pick a photo, GIF, or video and choose the faces you want to replace.

**CTA** — Start a Face Swap

**验收标准**

- 介绍区与现有工具页使用一致的版式、组件和移动端堆叠方式。两张配图分别讲清指定单人换脸和选取视频片段。
- 页面中的模式名称与工具界面一致。**Pricing** 和协议链接指向正式页面，底部 CTA 定位到当前页的换脸工具。
- FAQ 的可见文案和对应的 FAQ 结构化数据一致（如该页使用 FAQ 结构化数据）。

## 29｜补齐全站按钮的鼠标悬停反馈

**当前问题**

部分可点击按钮在鼠标移入时缺少可见的悬停效果。

**实现要求**

- 检查全站可点击按钮，覆盖主要按钮、次要按钮、图标按钮和弹窗按钮，补齐缺失的 hover 样式。
- 沿用现有按钮视觉规范，通过背景、边框或文字颜色变化提供清晰反馈。鼠标移出后恢复原有状态。
- 禁用按钮保持禁用外观，选中按钮的选中样式在悬停时仍清晰可辨。

**验收标准**

- 在桌面端逐一检查主要页面和弹窗。鼠标移入可点击按钮时可见样式变化，移出后正确恢复。
- 禁用按钮仍不可点击，选中状态与普通悬停状态可区分。

## 30｜统一首页底部 CTA 按钮的圆角

**修改位置**

首页底部 CTA 模块中的 **Start Free Now** 按钮。

**实现要求**

- 应用站内同类主按钮的圆角样式。优先复用共享按钮组件或现有圆角变量。
- 圆角在默认、悬停和键盘聚焦时保持一致。

**验收标准**

- 在桌面和移动端检查首页底部 CTA，确认 **Start Free Now** 与站内同类主按钮使用相同的圆角样式。

## 31｜补充 AI Movie 功能区下方的英文图文内容

**修改位置**

`/ai-movie/` 工具区下方、公共页脚上方。沿用其他工具页的三步流程卡片、图文模块、FAQ、相关工具和底部 CTA。将以下介绍内容放在公开 HTML 中，访客打开页面即可阅读。

### Make a Movie One Clip at a Time

AI Movie lets you build a movie from individual AI-generated clips. Add reference images for your characters, locations, and props, then reuse them across clips to help keep the look consistent. Describe what happens in each clip and join the clips into a movie when they’re ready.

### How to Make an AI Movie

1. **Add reference images**  
   Add the people, places, and objects you want to reuse. Give each reference a name so you can find it when you work on a new clip.
2. **Describe and generate each clip**  
   Describe one action at a time. Choose the references you need for that clip, set its duration and resolution, then generate it.
3. **Put your clips together**  
   Review each clip, arrange them in story order, and join them into one movie.

### Keep a Character Recognizable Across Clips

Reuse the same character reference whenever that character appears. For example, use one photo of a cyclist in a yellow jacket for three clips. In the first clip, the cyclist leaves a repair shop. In the second, they cross a bridge. In the third, they arrive at a lookout. Each clip has a different action and setting, with the same character reference throughout.

**配图要求** — 使用实际工具生成的三张示例帧，按故事顺序并排展示。同一角色在不同地点做不同动作，脸部和黄色外套保持可辨认。可在左侧放所用的角色参考图，标注 **Reference**，三张帧分别标为 **Clip 1**、**Clip 2** 和 **Clip 3**。  
**Alt text** — One cyclist reference image reused across three AI Movie clips at a repair shop, on a bridge, and at a lookout.

### Reuse a Location or Prop When It Matters

Add reference images for details that should carry over from one clip to the next. If two clips take place in the same café, reuse the café photo to help preserve its layout. If a red suitcase appears in several clips, reuse its reference and describe what the character does with it in each clip.

**配图要求** — 展示角色、咖啡馆和红色行李箱三类参考图，以及使用这些素材的实际片段帧。可用与现有界面一致的参考图区截图搭配生成结果。  
**Alt text** — Character, café, and red suitcase reference images shown beside the AI Movie clip that uses them.

### AI Movie FAQ

- **Do I have to write the whole movie in one prompt?** Write a short description for each clip, focusing on the action you want to see. Join the finished clips in story order.
- **How do I keep the same character across clips?** Reuse the same character reference wherever the character appears. If specific details matter, such as a yellow jacket or round glasses, mention them in the clip description.
- **Can I use reference images for locations and props?** Yes. Add a reference for a place or object you want to bring into a clip. Reuse that reference in later clips when the same detail should appear again.
- **How are credits charged?** Each clip is priced by duration and resolution. Check the credit cost before you generate. Joining clips into a movie is free. See **Pricing** for current rates.

### Explore More AI Tools

- **Image to Video** — Animate a still image and describe how it should move.
- **Text to Video** — Turn a written scene description into a video clip.

### Ready to Make Your Movie?

Start with a reference image and one action for your first clip.

**CTA** — Create Your Movie

**验收标准**

- 正文、操作步骤和 FAQ 在未登录时可读，服务端返回的 HTML 包含这些内容。
- 术语统一使用 **Reference Images**、**Clip / Clips** 和 **Movie**。两张配图能分别说明跨片段角色复用和场景、道具参考的用法，且有对应的英文 alt 文本。
- **Pricing** 链接指向价格页，底部 CTA 定位到当前页的 AI Movie 工具区。

## 32｜文生图和图片编辑统一为 10 积分/次

**定价**

| 功能 | 路径 | 每次任务所需积分 |
| --- | --- | ---: |
| Text to Image | `/text-to-image/` | 10 |
| Image Edit | `/image-edit/` | 10 |

**实现要求**

- 将两项功能的计价配置统一为每次任务 **10 积分**，确保提交前报价与实际扣费一致。
- 更新 **Pricing** 页 **Credit Costs by Tool** 下这两项的价格，以及各功能页的积分提示和确认弹窗（如有）。相关 FAQ、帮助文案或结构化数据中如有明确的旧价格，也同步更新。

**验收标准**

- Pricing 页和两个功能页的提交前报价均显示 **10 credits**。
- 分别完成一次文生图和图片编辑，确认每项任务实际扣除 10 积分，积分流水分别显示 **−10 credits**。
