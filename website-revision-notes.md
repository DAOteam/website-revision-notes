# 新站修改意见

审查站点：[新站](http://155.138.214.216:8090/)

## 68｜将等待处理页面的取消任务按钮上移

**状态：待修改。**

- 将当前位于 Premium Tools 引导卡片下方的取消任务按钮，移至任务进度区域下方、Premium Tools 引导卡片上方，紧接保持页面打开的提示之后。
- 桌面端和移动端均采用上述顺序，用户无需滚过整张 Premium Tools 卡片即可找到取消入口。
- 按钮文案为 **Cancel task**，沿用低强调的次要按钮样式，保持原有取消任务逻辑。

## 69｜免费任务展示固定规格并引导至高级图生视频页面

**状态：待修改。适用范围：免费图生视频任务表单，桌面端及移动端。**

- 移除 Resolution、Aspect Ratio、Duration 下模拟参数选择的按钮，包括带锁的 720p、1080p、9:16、1:1、10s、15s 选项。取消点击锁定选项直接跳转 Pricing 的交互。
- 改为普通文字或静态标签展示固定免费规格，不使用可点击或可解锁的样式：

  **Free video**  
  Low resolution · 16:9 · 5 seconds

- 在固定规格下方增加轻量高级功能引导，使用以下文案：

  **Want more control?**  
  Choose 720p / 1080p HD, different aspect ratios, and clips up to 15 seconds in Premium Tools.  
  **Open Premium Tools →**

- 点击入口直接前往高级 Image to Video 页面，并携带当前已上传的图片及已填写的提示词，用户无需重新上传或输入。仅填写其中一项时也应保留该项。
- 用户先在高级页面选择参数，准备生成时再根据登录状态及积分余额引导登录或购买。高级入口本身不直接跳转 Pricing。
- 验收：未登录、已登录且积分不足、已登录且积分充足时，入口均到达高级图生视频页面；验证图片及提示词正确保留，免费任务仍可按固定规格正常提交。

## 70｜免费模块及引导卡片统一使用 Premium Tools

**状态：待修改。适用范围：免费任务表单、等待处理页及免费作品生成后的引导卡片，包含桌面端和移动端。**

- 高级功能统一称为 **Premium Tools**，替换上述范围中的 Pro、Pro tools 等称呼，保持相同拼写及大小写。
- 免费表单引导文案使用 **in Premium Tools**，入口使用 **Open Premium Tools →**，仍直达高级 Image to Video 页面并携带图片及提示词，遵循第 69 项。
- 等待处理及免费结果卡片中的 **Go Pro**、**Explore Pro** 按钮改为 **Explore Premium Tools**。**Go Pro for priority processing and more ways to create.** 改为 **Use Premium Tools for priority processing and more ways to create.**
- 现有卡片中其他标题、正文、按钮若仍使用 Pro，也需一并调整。例如 **Waiting too long? Go Pro** 改为 **Waiting too long? Try Premium Tools**；**Upgrade to Pro for stunning quality** 改为 **Create better videos with Premium Tools**。不得仅替换免费表单入口而遗漏引导卡片。
- 保留卡片已有权益及价格信息；本项统一功能名称，不将 Premium Tools 表述为购买后在免费表单内解锁的选项。

## 71｜修复未登录时图生视频及 AI Movie 描述 Guide 无法关闭并阻断页面操作

**状态：待修复。优先级：高，阻断页面操作。适用范围：图生视频及 AI Movie 页面的描述 Guide，桌面端及移动端。**

- 用户反馈：图生视频和 AI Movie 页面均存在此问题。未登录时先打开描述区域的 **Guide**（标题 **How to Write Your Description**），点击右上角关闭按钮或 **Got it**，Guide 未关闭，反而在其背后出现登录弹窗，导致所有操作被阻断。
- 复现步骤：在未登录状态分别进入图生视频和 AI Movie 页面，先点击描述 Guide，分别尝试关闭按钮及 Got it，观察弹窗是否关闭、是否出现登录弹窗及页面能否继续操作。
- Guide 的打开、关闭及 Got it 操作无需登录。关闭按钮与 Got it 均直接关闭 Guide，不触发登录、不提交生成任务，也不将点击传递到背后的页面控件。
- 关闭后正确清理 Guide 的遮罩、焦点限制及滚动锁定，恢复页面点击、输入和滚动；保留已上传图片及已填写描述。
- 排查关闭事件是否误触发登录校验、表单提交或点击穿透，以及弹窗层级和状态管理。上述为待排查方向，不预设已确认根因；修复不能仅提高登录弹窗层级。
- 验收：图生视频与 AI Movie 两个页面均需分别在桌面端和移动端验证。未登录状态下，首次打开及反复打开 Guide，分别用关闭按钮和 Got it 均可正常退出且不出现登录弹窗；退出后表单可操作。已登录状态同步回归，正常需要登录的生成操作仍按原规则处理。

## 72｜移除 AI Movie 标题区的 Sign in to start 按钮

**状态：待修改。适用范围：AI Movie 页面，桌面端及移动端。**

- 删除截图中页面介绍区域右侧的 **Sign in to start** 按钮，即 **Make a movie with consistent characters** 标题旁的登录按钮。
- 顶部导航栏的 **Sign In** 入口保留，原有需要登录的功能继续按既有规则处理。
- 移除按钮后调整标题区布局，不保留按钮占位或多余留白；核对未登录状态下桌面端与移动端均不再显示该按钮。

## 73｜全站下载按钮直接下载文件

**状态：待修复。适用范围：全站所有下载按钮及下载菜单入口，桌面端及移动端。**

- 用户反馈：免费任务完成后的 **Download Video** 点击后仅打开视频播放页面，未直接下载。
- 统一行为：点击下载直接触发对应文件的浏览器下载或系统保存流程，不跳转当前页面、不新开播放页，也不要求用户在播放器中再次寻找下载入口。
- 覆盖免费任务结果页、Premium Tools 各工具结果、作品列表或详情中的下载入口、AI Movie 单个 Clip 的 Preview/HD 及整片合并导出文件等全站下载位置；按各入口对应的实际文件及版本下载，文件名与扩展名正确。
- 排查直链导航、跨域媒体及存储响应头导致的内联播放问题。使用可靠的附件下载响应（例如正确的 Content-Disposition）或合适的下载实现，不能仅为跨域直链添加 download 属性后即视为修复。大文件下载应避免不必要的全量内存占用。
- 下载请求失败或文件失效时给出明确错误并允许重试，不静默跳转到播放页，不保存错误响应为视频或图片文件。
- 验收：逐一检查全站下载入口，在桌面端 Chrome、Safari 及移动端 iOS Safari、Android Chrome 验证实际保存流程；覆盖免费视频、付费工具图片/视频、AI Movie 单段及整片导出等现有类型，并验证跨域存储文件能下载、所得文件可正常打开。移动端遵循系统保存交互。

## 74｜精简免费作品生成后的 Premium Tools 引导卡片

**状态：待修改。适用范围：免费视频生成结果页，桌面端及移动端。**

- 删除重复的皇冠口号与升级标题，保留一个主标题，突出高清、人物说话及无水印。免费分辨率统一使用 low resolution，不再写 480p。
- 使用以下最终文案（名称遵循第 70 项）：

  **Ready for a better video?**

  Create in 720p / 1080p HD with character dialogue, sound effects, and no watermark.

  Your free video is low resolution, silent, and watermarked.

  - **720p / 1080p HD** — sharper details
  - **Audio generation** — synced character dialogue and sound effects
  - **No watermarks** — includes commercial use
  - **Priority queue** — faster generation
  - **All AI tools** — AI Movie, video, image, editing, Face Swap
  - **Up to 10 tasks at once**

  按钮：**Explore Premium Tools — from $15.99**。价格仍使用实际起售价，不硬编码失效价格。

- 将原 **No queue — instant generation** 改为上述 Priority queue 文案，避免立即出结果的承诺。
- 桌面端权益采用两列，移动端采用一列。图标统一与每条文字的第一行对齐；前三项优先展示，减少长句和卡片高度。
- 本项与第 70 项的示例标题不一致时，以本项最终文案为准。

## 75｜调整等待处理页的 Premium Tools 引导卡片文案

**状态：待修改。适用范围：免费任务等待处理页，桌面端及移动端。**

- 主标题：**Less waiting. More creating.**
- 说明：**Use Premium Tools for priority processing and more ways to create.**
- 桌面端保留两列、每列三项；同一行内容顶部对齐，图标与各项第一行对齐。移动端按实际宽度自适应，避免文字及按钮溢出。

| 左列 | 右列 |
| --- | --- |
| **Priority queue**<br>Get ahead of free tasks | **720p / 1080p HD**<br>Sharper, clearer videos |
| **Dialogue & sound**<br>Synced character voices and sound effects | **All AI tools**<br>AI Movie, video, image, editing, Face Swap |
| **Longer videos**<br>5–15 seconds per clip. Create movies of any length with AI Movie. | **Preview first**<br>Check your clip before generating in HD |

- 用户确认 **Preview first** 为高级功能，保留该权益。Longer videos 必须同时表达每段 5–15 秒以及 AI Movie 可创作任意长度的电影。
- 按钮：**Explore Premium Tools**。
- 底部小字：**Free videos are 5 seconds, low resolution, and silent.**
- 本项与第 70 项的示例标题不一致时，以本项最终文案为准。取消任务入口按第 68 项放在本卡片上方。

## 76｜免费任务按时间排队，符合条件的访客注册领取 60 积分

**状态：待修改。适用范围：免费任务排队及新用户注册赠送流程，桌面端和移动端。**

### 排队与邀请资格

- 所有用户的免费任务默认按任务发起时间先后排队，不因 IP 判断结果自动插队。IP 判断决定是否提供注册领取 Premium Tools 积分的邀请资格，不直接加速原免费任务。
- 后端根据 IP 判断资格。具体识别规则复用业务配置，不在本项中臆造国家、地区或次数阈值；领取时结合账户及领取记录校验，同一资格不得重复发奖。
- 仅对符合资格且尚未登录、免费任务仍在排队的访客自动弹出邀请。同一任务不反复自动弹出；关闭弹窗或选择继续等待，保留原任务及排队位置。
- 已经开始生成或已结束的任务不触发此邀请。本项替代此前讨论的广告、分享助力方案，不接入广告或好友助力。

### 邀请弹窗最终文案

**Try Premium Tools with 60 free credits**

Your free video is currently **#{queue_position} in the queue**.

Create an account to claim 60 free credits for Premium Tools. Once you claim your credits, your current free task will be canceled.

主按钮：**Create account & claim 60 credits**

次按钮：**Keep waiting for free**

补充说明：**Your free task will stay in the queue until you finish signing up and claim your credits.**

- 队列位置由后端实际状态提供并刷新，不使用固定示例排名或虚构等待时长。
- 点击主按钮进入注册流程，明确关联当前排队任务与赠送资格。完成注册和领取前，不因该按钮操作提前取消任务；用户退出、注册失败或领取失败时不主动取消原任务。
- 从此邀请进入的正常注册流程不应因注册弹窗或身份验证跳转触发离开页面 2 分钟的取消规则，以免与上述保留承诺冲突；普通离线规则不在本项中另行改造。

### 注册领取成功后的处理

- 注册成功后自动完成资格校验及 60 积分领取，无需用户再找领取按钮。确认积分真实到账且原任务仍可取消后，完成取消原免费任务和兑换处理，避免只取消却未发奖。
- 实现重复请求保护；重复点击、刷新、多个标签页或注册回调重放均不得重复发放 60 积分。赠送记录与账户余额一致，领取失败提供真实状态及重试入口，不显示虚假到账提示。
- 注册期间任务若已经进入生成或已完成，重新校验状态，不强行取消已经开始的任务；明确提示当前任务状态，不显示“已取消”的兑换成功文案。
- 正常兑换成功后自动显示以下到账弹窗：

**You’ve received 60 free credits!**

Your free task has been canceled. Use your credits to create with Premium Tools.

按钮：**Explore Premium Tools**

- 仅在确认发放成功后显示获得 60 积分；不要把已有账户登录成功当作新用户注册领取成功。
- 此领取流程不自动携带或迁移原图片、描述，也不承诺已保存到 Premium Tools；不显示 **Your image and description are ready in Premium Tools.** 或同义文案。此约束专用于本项注册领取流程。
- 点击 Explore Premium Tools 进入现有 Premium Tools 入口，用户自行选择功能、上传素材并填写描述；不自动创建高级生成任务、不自动扣积分。

### 验收

- 覆盖符合资格与不符合资格的 IP、邀请关闭、继续排队、注册放弃/失败、领取失败、正常注册到账、重复领取及多标签页，以及注册期间任务已开始/完成的情况。
- 正常兑换后原免费任务不再占用队列或继续生成，账户仅到账一次 60 积分；成功弹窗自动出现且可正常关闭，图片和描述不自动迁移。
- 桌面端及移动端完整验证注册返回、任务状态、队列实际排名、赠送余额与弹窗文案一致。
