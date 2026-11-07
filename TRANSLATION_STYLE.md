# BFV ROBOT 文案与翻译规范

本规范适用于界面、帮助中心、公开 API 文档和机器人相关的网站说明。简体中文是源语言；繁体中文、日语和英语保持相同的业务含义。翻译可以调整语序，不能改变权限、限制、期限或操作结果。

## 文案原则

- 先写用户需要知道的结果，再写下一步。用“凭据已过期，请更新凭据”，不写“发生未知问题，请检查相关配置是否正确”。
- 按钮写动作和对象，例如“保存设置”“领取案件”“删除蓝图”。标题与按钮不重复叙述同一段流程。
- 状态准确区分“正在处理”“已提交”“已完成”“结果待确认”。请求已提交、取得 Game ID、平台已接收都不等于最终操作完成。
- 删除与当前任务无关的开发过程说明，例如“本轮新增”“下一阶段接入”“这里不会读取数据”。配置方式、诊断信息与接口约定放在需要它们的开发者区域或帮助中心。
- 基础查询页不反复标注“所有人可调用”“公开查询，无需登录”。操作受限时明确说明所需角色、绑定或授权。
- 不使用夸大承诺，例如“绝对安全”“永久可用”“百分百成功”。期限属于站内规则时，不能改写成第三方平台的保存保证。
- 面向用户的名称使用“账号”，不在同一流程混用“账号／账户”。货币系统未来若需要区分钱包或账务账户，应另建术语。

## 术语表

| 含义 | 简体中文 | 繁體中文 | 日本語 | English |
| --- | --- | --- | --- | --- |
| Website account | 社区账号 | 社群帳號 | コミュニティアカウント | Community account |
| Game service account | 游戏账号 | 遊戲帳號 | ゲームアカウント | Game account |
| Website work item | 案件 | 案件 | 案件 | Case |
| Platform support channel | 票证 | 票證 | チケット | Ticket |
| Claim responsibility | 领取案件 | 領取案件 | 案件を担当する | Claim case |
| Move responsibility | 转交案件 | 轉交案件 | 案件を引き継ぐ | Transfer case |
| Connect an identity | 绑定 | 綁定 | 連携 | Link |
| Disconnect an identity | 解除绑定 | 解除綁定 | 連携を解除 | Unlink |
| Sign in | 登录 | 登入 | ログイン | Sign in |
| Sign out | 退出登录 | 登出 | ログアウト | Sign out |
| Game performance | 战绩 | 戰績 | 戦績 | Stats |
| Platoon | 战排 | 戰排 | 小隊 | Platoon |
| Match side | 队伍 | 隊伍 | チーム | Team |
| Prevent server entry | 屏蔽 | 屏蔽 | BAN | Ban |
| Remove from current game | 踢出 | 踢出 | キック | Kick |
| Authenticate or prove | 验证 | 驗證 | 認証・検証 | Verify |
| Approve submitted content | 审核 | 審核 | 審査 | Review |
| Reconcile an uncertain result | 核对 | 核對 | 結果を確認 | Verify result |
| Suspected or confirmed cheating | 疑似或确认作弊 | 疑似或確認作弊 | 不正行為の疑い・確定 | Suspected or confirmed cheating |
| Serious rule violation | 严重行为违规 | 嚴重行為違規 | 重大な行為違反 | Serious misconduct |
| Lite edition | 精简版 | 精簡版 | 簡易版 | Lite |
| Advanced edition | 进阶版 | 進階版 | 上位版 | Advanced |
| Full edition | 完整版 | 完整版 | 完全版 | Full |
| Warmup | 暖服 | 暖服 | サーバーのウォームアップ | Warmup |

“案件”是站内业务记录，“票证”是平台上的支持流程，二者有关联但不混用为两个互不关联的系统。“石锤”“刷枪”等旧 key 仍可为兼容保留；翻译不能直译为 stone hammer、brushing 或石のハンマー。游戏行为需要根据上下文译为确认作弊、武器进度或验证结果。

战排日文“小隊”参考 [EA 的 Platoons 说明](https://www.ea.com/ja-jp/games/battlefield/news/introducing-platoons-in-battlefield-1)。不要将它与当前对局中的队伍或分队混为一谈。

## 名称与格式

- 保留 BFV ROBOT、CAT TEAM、Battlefield V、EA、Blaze、Cloudflare、Turnstile、GeeTest、hCaptcha、reCAPTCHA、KOOK、Discord、Steam、BFBAN、MOSS 的官方拼写。
- 小黑盒账号平台用 HEYBOX；黑盒语音用 HeyChat。二者不是同一个登录或机器人服务，不能互换名称。
- API、PID、UID、ID、OpenID、OAuth、TOTP、SMTP、SQL、JWT、URL、WebSocket、PC Token、gRPC、Protobuf 保留规范大小写。英语写 API token、bot token；协议或代码中的字段名原样保留。
- 英文标题、表头与按钮使用 sentence case，例如“Server settings”“Claim case”。不使用装饰性全大写，也不把每个单词都首字母大写。
- 中文与英文缩写、数字之间保留适当空格，例如“QQ 群”“8 MiB”“3 小时”。日语使用自然语序，避免从中文逐字翻译。
- 数字零是有效数据；缺失数据与未知结果写“—”“尚未取得”或明确状态，不改成零、正常或成功。
- 单位、时区、最大值与最小值必须与功能约定一致。3 年、10 年表示站内保留期限；外部链接可能先于该期限失效。

## 错误、权限与确认

必要的恢复信息不能为了简短而删除：

1. 登录或凭据失效时，说明需要更新凭据、重新登录或在 EA 完成验证。
2. 上传、广播、开服、写入结果未确认时，先核对状态，明确不要立即重复提交。
3. 删除蓝图、移除成员、清除凭据、转移群主、撤销 Token 等操作，保留对象、后果与确认动作。
4. 验证方式之间可以替代时，写明“任选一种”；不得把 Passkey 与 TOTP 描述成必须依次完成。
5. 验证码豁免不等于权限豁免。无需在每张表单重复解释实现，但安全中心和帮助中心必须说明边界。
6. 正式的服务器规则同意、隐私政策、授权范围和恢复码警告保留实质内容。改写前先核对实际行为，不能以润色为由改变规则。

## Catalog 与 Crowdin 约定

全部可翻译文案集中在 `app/locales/*.json`，包括 `guide.*`、`baidu.*` 和 `apiDocs.*`。内嵌的四语字典不得成为独立翻译源。Crowdin 只接收字符串；不得上传源码、私有配置、真实凭据、内部地址或包含敏感数据的截图。

- 新文案使用稳定的语义 key，例如 `link.translationTitle`。修改显示文案时不改 key，不用新英文译文作为 key。
- 已有中文 literal key 保持兼容。改变它的中文 value 即可更新文案；不要删除 key 来隐藏组件，也不要用空字符串绕过渲染。
- 要删除冗余说明，必须同时删除页面节点。失效或空白翻译会触发回退，无法可靠隐藏内容。
- `{name}`、`{count}`、`{personaId}` 等占位符的名称和数量不可更改。所有语言必须与源文一致，可以调整出现顺序。
- 保留代码块、行内代码、链接目标、接口路径、参数名、scope、HTTP 状态码、Header 名称与示例语法。只翻译说明，不翻译协议。
- `账号,密码,密钥` 是当前 CSV 导入要求的字面表头；英文与日语仍保留这三个中文列名。命令示例中的中文指令也可以保留，不能为了消除汉字而破坏可执行示例。
- 新语言采用规范的 BCP 47 文件名，例如 `fr-FR.json`。只有经审核并纳入构建的文件才会成为网站语言；缺失或占位符不符的翻译使用源语言回退。
- 翻译提交、语言加入和生产发布遵循仓库的审核流程。翻译者不得通过文案加入脚本、凭据、未审核链接或声称不存在的功能。

## 审校与验收

每次批量修改后核对四类内容：

- 结构：JSON 有效、key 唯一、旧 key 未意外删除、四语 key 集合一致。
- 格式：占位符一致、协议片段保留、HTML/Markdown 符合当前渲染方式，不插入未经审核的外部链接。
- 语义：权限与限制未放宽，错误未译为成功，未知结果的防重试提醒仍在。
- 界面：检查主要语言的导航、表格、对话框和移动端长文本；按钮允许自然换行，不能依赖中文短标签固定宽度。

每次发布由管理员核对 catalog 结构、占位符和高频操作文案；专业游戏术语仍需要相应语言的校对者审阅。
