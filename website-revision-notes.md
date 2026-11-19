# 新站修改意见

审查站点：[新站](http://155.138.214.216:8090/)

## 59｜核对 AI Movie 作品倒计时与实际到期时间

**状态：待验证。**

- 核对作品卡片剩余时间以该作品的实际到期时间为准。显示格式例如 **85d left**。

## 60｜补齐首页免费结果页的静音说明

**状态：待修改。**

- 首页免费任务结果页的 Pro 权益卡片，音频文案末尾补上 **(silent on free)**，完整文案为 **Audio generation — synced character dialogue and sound effects (silent on free)**。

## 62｜补验 AI Movie 批量生成 HD 的确认和异常流程

**状态：待验证。**

- 在 **Whole movie → Preview** 核对批量入口及确认框。入口为 **Generate All Clips in HD**，显示可生成的片段数和总积分。仅包含已有 Preview 且尚无 HD 的片段，跳过已有 HD 和缺少 Preview 的片段。
- 确认框列出片段、生成顺序、电影分辨率、总积分及跳过原因。确认按钮显示实际数量和积分，例如 **Generate 3 Clips · 120 credits**。余额不足时显示差额，并阻止提交。
- 补验重复提交保护。已排队或正在生成 HD 的片段，应在单段页显示相应状态并阻止重复提交。
- 补验失败重试。后续片段依赖失败片段的 HD 时暂停，提供对应片段的重试入口，成功后自动继续。后续片段可独立生成时继续处理，最后提供 **Retry Failed Clips**。保留已完成的 HD。
- 补验本批完成但全片仍缺少 Preview 的情况，应显示实际完成数量和待预览片段。全片每个 Clip 都有 HD 时才显示 **All clips are ready in HD** 并提供 **Watch Full Movie in HD**。

## 63｜补验 AI Movie Preview 合并及最终失败提示

**状态：待验证。**

- 补验 **Preview** 整片导出。浏览器合并切换到服务器时，页面显示 **Joining…** 和用时，移除 **Couldn’t join the clips in this browser — joining them on our server instead.** 及同义提示。完成后提供预览版下载入口。
- 补验服务器最终合并失败时，页面仍显示最终错误。

## 66｜补验重新生成中间 Clip 后的视频保留规则

**状态：待验证。**

- 完整提交一次中间 Clip 的 Preview 重生成。新 Preview 成功生成后替换当前旧 Preview，并移除当前 Clip 已有的 HD。生成失败时保留当前旧 Preview 和 HD。
- 后续每个 Clip 已生成的 Preview 和 HD 都必须保留。重生成成功后逐个打开后续片段，确认原有 Preview 和 HD 仍可播放。
- 补验警告触发范围。任一后续 Clip 已有 Preview 或 HD 时，均需先弹出警告，包括后续只有 Preview、只有 HD、隔段已有结果，以及当前 Clip 有无 HD 的情况。后续均无结果的情况也需核对。

## 67｜补验未登录状态下的移动端页面标题

**状态：待验证。适用范围：移动端功能页及 Pricing 页。**

- 未登录时在移动端切换功能页与 **Pricing** 页。顶栏显示对应页面名称，例如 **Image Edit**、**Image to Video**、**AI Movie**、**Pricing**。
- 标题相对于整个顶栏水平居中、垂直对齐，与左侧菜单及右侧登录入口互不遮挡，两侧入口可点击。
