# 新站修改意见

审查站点：[新站](http://155.138.214.216:8090/)

仅保留未完成及待验证内容，沿用原编号。窄屏检查不等同于手机真机或跨浏览器验收。

## 88｜保留批量 HD 的 Pause 按钮，暂停前说明范围并确认

**状态：待修改。本项替代此前删除 Pause 按钮的方案。适用范围：AI Movie 批量生成 HD 后，页面右上角自动生成状态栏，桌面端及移动端。**

- 保留 **Pause** 按钮、状态指示点、片段进度及相邻更多菜单。点击 Pause 先弹出确认弹窗，不立即暂停。
- 弹窗标题：**Pause HD generation?**
- 弹窗正文：**The clip currently generating cannot be paused and will continue to completion. Only the remaining clips that haven’t started will be stopped. You won’t be charged for those clips.**
- 两个按钮：**Cancel**（取消）及 **Continue pausing**（继续暂停）。点击 Cancel、关闭弹窗或按 Escape 均不改变批量任务状态，继续原流程；只有点击 Continue pausing 才执行暂停。
- 确认后停止后续尚未开始生成的 Clip，包括本批次中可撤出的等待片段，防止当前 Clip 完成后自动启动下一段。已经实际开始生成的 Clip 不能暂停或取消，继续完成并按实际结果正常结算；已成功的 Clip 保留结果及扣费。
- 后续未开始的 Clip 不收费：尚未扣费的不扣费，若已预扣或预留则退还或释放对应积分，仅处理这些未开始片段，不能整批退款。重复点击、重复请求或回调不得导致重复退款。
- 确认时由后端重新核实各 Clip 状态，并与下一段的启动协调，避免弹窗打开期间状态变化导致误停已开始任务。若某段已实际开始，则继续完成并如实更新状态；确认生效后不再启动其余未开始片段。
- 暂停成功后的页面不能暗示当前生成已停止；若仍有 Clip 正在生成，明确显示 **Current clip is still generating. Remaining clips are paused.** 并继续更新真实进度。仅在后端确认成功后显示暂停结果，失败时提示并允许重试。
- 验收：覆盖弹窗取消/关闭、继续暂停、当前生成中且后续待执行、后续已预扣积分、确认前任务恰好切换到下一段、重复点击及暂停失败；当前已开始任务继续，后续不再启动，未开始片段不收费且退款不重复，桌面端和移动端一致。

## 89｜后续 Preview 成功后锁定前序 Clip，添加新 Clip 前提醒确认

**状态：待修改。适用范围：AI Movie 的 Clip 编辑、Preview 生成及 Add Clip，桌面端及移动端。本项替代此前允许在后续已有 Preview 时重新生成前序 Preview 的方案。**

- 一旦 Clip N 的 Preview 成功生成，禁止修改及重新生成它之前所有 Clip 的 Preview。对当前 Clip 检查是否存在任意后续已成功生成的 Preview，不能仅检查是否为当前选中片段，或仅检查相邻下一段。
- 锁定包含用户描述、时长及其他会改变该段 Preview 的生成设置，以及 Preview 首次提交/重新生成等可绕过锁定的入口。锁定处提供简短原因：**This clip is locked because a later clip already has a preview.**
- 保留已锁定片段的查看、播放、下载及生成 HD 等操作；本项限制 Preview 编辑和重新生成，不禁止基于现有 Preview 生成 HD，不删除已有素材或结果。
- 锁定时点为后续 Preview 生成成功，而非仅添加空 Clip、填写描述、生成专业提示词或提交任务。后续尚在生成时继续遵守现有生成依赖校验，不能通过并发提交破坏前后段引用关系。
- 点击 **Add Clip** 时，在实际新增前显示确认弹窗，提醒用户检查当前最后一段；保留“最后一段需先成功生成”的既有校验，校验不满足时先提示原因，不新增片段。
- 弹窗标题：**Ready to add the next clip?**
- 弹窗正文：**Once the next clip’s preview is generated, you won’t be able to edit or regenerate previews for any earlier clips. Please make sure Clip {number} doesn’t need any more changes before continuing.** 编号使用当前最后一段的实际编号。
- 弹窗复选框：**Don’t show this again**，默认不勾选。按钮为 **Cancel** 和 **Add Clip**。取消、关闭或 Escape 均不新增 Clip；确认后才新增一次，不自动发起生成或扣费。
- 用户勾选 Don’t show this again 并确认 Add Clip 后，持久保存该提示偏好，后续新增可跳过弹窗；取消不保存本次偏好。隐藏提醒不影响真实锁定规则及最后一段生成状态校验。
- 前后端统一执行锁定校验，覆盖刷新、多标签页、历史任务及自动流程；不能只隐藏按钮或将输入框置灰，仍允许旧请求改写前序 Preview。成功状态变化后及时更新界面。
- 验收：覆盖后续空草稿、生成中、失败和成功；只有后续成功时按规则锁定所有前序 Clip。覆盖添加前确认、取消、不再提示及刷新后偏好保留，重复点击不新增多段；锁定后编辑/重新生成被拦截，HD 生成、已有结果播放及下载正常。
