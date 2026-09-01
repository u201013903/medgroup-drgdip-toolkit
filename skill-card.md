## Description: <br>
MedGroup DRG/DIP 医保分组助手。安装技能后，通过 MedGroup 登录授权使用城市与规则查询、ICD 检索、DRG/DIP 分组、结算情景测算和 CC/MCC 查询。 <br>

This skill is ready for commercial/non-commercial use. <br>

## Publisher: <br>
[u201013903](https://clawhub.ai/u201013903) <br>

### License/Terms of Use: <br>
MIT-0 <br>

## Use Case: <br>
Healthcare operations users install one skill in WorkBuddy or another compatible client, authorize their own MedGroup account, and use the following remote tools: `get_city_list`, `search_icd`, `drg_grouping`, `dip_grouping`, `calculate_settlement`, `find_code_info`, `get_rule_details`, `check_dip_rule`, and `get_cc_status`. <br>

### Deployment Geography for Use: <br>
Global <br>

## Known Risks and Mitigations: <br>
Risk: Grouping, settlement, and code-status requests may contain medical parameters. <br>
Mitigation: Use synthetic or de-identified data for setup and validation. Do not send patient names, identity numbers, contact details, admission numbers, or other direct identifiers. Review the MedGroup privacy policy and applicable organizational requirements before using real business data. <br>
Risk: Authorization does not guarantee that a business call will succeed. Account status, granted scope, and available AI interaction quota are checked for each call. <br>
Mitigation: Follow the client login flow, review the requested tool permissions, and use MedGroup authorization management to revoke access when it is no longer needed. <br>

## Reference(s): <br>
- [MedGroup homepage](https://medgroup.medchat.fun) <br>
- [MedGroup privacy policy](https://medgroup.medchat.fun/privacy-policy) <br>
- [MedGroup terms of service](https://medgroup.medchat.fun/terms-of-service) <br>
- [MedGroup authorization management](https://medgroup.medchat.fun/settings/connections) <br>
- [ClawHub skill listing](https://clawhub.ai/u201013903/skills/medgroup-drgdip-skill) <br>

## Skill Output: <br>
**Output Type(s):** [Text, JSON, API Calls, Guidance] <br>
**Output Format:** [Markdown guidance with structured MedGroup tool responses] <br>
**Output Parameters:** [1D] <br>
**Other Properties Related to Output:** [Requires a compatible client to load the bundled remote MCP configuration and complete MedGroup OAuth authorization.] <br>

## Skill Version(s): <br>
Use the ClawHub server release metadata as the version source of truth. <br>

## Ethical Considerations: <br>
Results support DRG/DIP grouping and coding review only. They do not replace clinical diagnosis, final medical-record coding, payer review, or official local settlement documents. Users should review tool results and apply their organization's security, privacy, and compliance requirements. <br>
