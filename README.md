# DRG/DIP 工具包（MedGroup）

MedGroup 面向 DRG/DIP 医保支付与编码复核场景提供远程 MCP 工具。用户安装 OAuth 版技能或导入自定义连接器配置后，通过本人 MedGroup 账号完成授权，无需复制 API Key，即可在对话中查询城市与规则、检索 ICD 编码、执行 DRG/DIP 分组、进行结算情景测算并查询 CC/MCC 状态。

## WorkBuddy 接入信息

- 展示名称：`DRG/DIP 工具包（MedGroup）`
- 内部标识：`medgroup-drgdip-toolkit`
- MCP 地址：`https://medgroup.medchat.fun/mcp/oauth`
- 传输方式：Streamable HTTP
- 认证方式：MCP OAuth 2.1（Authorization Code + PKCE S256）
- 权限范围：`medgroup:mcp:core`
- 官网：<https://medgroup.medchat.fun>
- 隐私政策：<https://medgroup.medchat.fun/privacy-policy>
- 服务条款：<https://medgroup.medchat.fun/terms-of-service>
- 授权管理：<https://medgroup.medchat.fun/settings/connections>
- 支持地址：<https://medgroup.medchat.fun/feedback>

## 工具能力

连接器当前提供 9 项核心能力：城市/规则版本查询、ICD 编码检索、DRG 分组、DIP 分组、结算情景测算、编码规则信息查询、DRG/DIP 规则详情、DIP 规则核对与 CC/MCC 状态查询。具体工具名称、参数和用途以 MCP 运行时 `tools/list` 为准，本仓库不另行维护一份参数 schema。

## 使用流程

1. 在 ClawHub/SkillHub 安装或更新 `@u201013903/medgroup-drgdip-skill`，确认版本不低于 `1.1.0`。如客户端暂不会自动加载技能内的 MCP 配置，导入本仓库的 `mcp.json`。
2. 发起第一次真实工具调用，按客户端提示登录 MedGroup 并确认授权。
3. 在工作任务中询问：`你是否可以看到 MedGroup 相关工具？请逐一列出工具名称和用途。`
4. 再要求调用 `get_city_list`，核对真实工具轨迹和 MedGroup 业务响应。

WorkBuddy 官方连接器市场仍在申请中；本仓库和 ClawHub 技能发布不代表已通过 WorkBuddy 官方审核或已在其连接器市场公开可搜。

仅查看工具列表不扣减 MedGroup 额度；每次真实工具调用按 MedGroup 当前会员与额度规则校验。

## 数据与专业边界

请优先使用合成或脱敏数据，不要提交患者姓名、身份证号、联系方式、住院号等可直接识别个人身份的信息。结果用于医保分组、编码复核和结算情景辅助，不替代临床诊断、病案编码终审、医保审核或主管部门认定。

## English description

MedGroup provides a remote MCP toolkit for DRG/DIP payment, coding review, grouping, rule lookup, settlement scenario calculation, and CC/MCC status checks. WorkBuddy users connect the toolkit and authorize their own MedGroup account through OAuth 2.1 with PKCE, without copying or sharing an API key. The server exposes its current tool schemas through the MCP `tools/list` response and applies MedGroup account, membership, and quota rules to each real tool call.

## 文件说明

- `mcp.json`：WorkBuddy 远程 MCP 地址，不包含密钥。
- `connector-entry.json`：提供给 WorkBuddy 审核方的建议市场元数据。
- `SKILL.md`：关联技能的任务识别、参数追问和错误处理规则。
- `skill-card.md`：公开技能平台说明。
- `icon.png`：400×400 透明背景 PNG 图标。
