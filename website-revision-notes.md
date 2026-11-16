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
