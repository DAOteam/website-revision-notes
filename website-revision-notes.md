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
