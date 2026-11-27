
# Muse（缪斯）· 个人学习管家

Muse 把微信通知、课表和文档整理成有出处的待办、复习计划和每日简报。老师临时改了截止时间时，可以回查原话，再确认现在该做什么。完整版包含 16 个 Agent Skills。

## 下载和开始使用

1. 下载 [Muse_3.0.3.zip 完整版](https://github.com/tangxuhang/muse-student-skills/releases/download/v3.0.3/Muse_3.0.3.zip)，解压到新目录。
2. 用支持 Agent Skills 的工具打开解压后的「提交」目录，保留其中的 `.agents`。
3. 要在旧版目录继续使用时，按 [v3.0.3 发布页](https://github.com/tangxuhang/muse-student-skills/releases/tag/v3.0.3) 选择补丁。直接安装完整版无需应用补丁。

GitHub 的绿色 Code 菜单下载的是仓库快照。安装请使用上面的完整版附件。

## 微信记录怎么提供

- 有 TXT、HTML、聊天 JSON 或带时间和发言人的原话，直接交给 Muse。
- 记录仍在微信时，完整版优先使用内置 `wechat-local-data-export`。请指定会话和日期。该功能需要 Windows x64、64 位 Python 3.13，以及本人已登录的电脑版微信。
- 当前环境用不了内置导出时，可先粘贴相关原话。需要在另一台 Windows 电脑批量导出时，可用独立的 [微信聊天记录导出工具](https://github.com/tangxuhang/wechat-export-tool/releases)。

## 用样例体验一次

打开「提交」目录后，可以直接对 Agent 说：

> 读取 `.agents/examples/campus-notices.md`，找出实验二最终截止时间、改期原话和我还需要做的事，再整理成行动清单。

样例的截止时间从 **11 月 17 日 17:00** 延至 **18:30**，提交平台保持不变。「资料领取回执」已有提交记录。可据此核对回答是否找对了改期依据和未完成任务。

## 16 个 Skill 功能索引

| 模块 | Skill | 需要什么 | 能得到什么 |
| --- | --- | --- | --- |
| 资料接入 | **微信记录导出** `wechat-local-data-export` | 本人已登录的 Windows 微信、指定会话和时间范围 | 聊天导出为 HTML、TXT，可选离线语音转写。群成员名单导出为 Excel，也可导出本机已有附件 |
| 资料接入 | **多格式资料转写** `normalize-materials` | 聊天档案、文档或表格 | 带来源定位的 Markdown 或 JSON，可阅读、搜索和进一步处理 |
| 会话理解 | **重点信息汇总** `chat-attention-brief` | 一段时间内的群聊、私聊或通知 | 按重要程度整理的简报，标出重点和后续变更 |
| 会话理解 | **事项溯源** `chat-event-replay` | 一个具体事项和相关聊天记录 | 从提议、确认到改期、取消或完成的时间线，附可回查的原消息 |
| 会话理解 | **群聊分工图** `group-collaboration-map` | 群成员名单或群聊档案 | 负责人、角色、交接关系及待核实事项 |
| 会话理解 | **群聊知识整理** `chat-knowledge-curator` | 群里的问答、规则、经验和决定 | 可复用的 FAQ、操作流程和结论，保留出处 |
| 会话理解 | **双方关系分析** `social-relation-radar` | 指定对象的聊天档案及可核实的共同群聊 | 分时间段核对双方互动，给出行为证据和对应消息 |
| 会话理解 | **沟通参谋** `relationship-advisor` | 对话片段、沟通目标和个人偏好 | 不同解读、回复建议和后续沟通选项 |
| 学习与计划 | **会话任务调度** `wechat-skill-coordinator` | 目标及已有聊天或资料 | 选择对应 Skill，按会话复核原话，汇总为个人计划 |
| 学习与计划 | **行动清单** `extract-action-items` | 已核对的通知、承诺和回执 | 带负责人、截止时间、来源和状态的待办 |
| 学习与计划 | **校园管家** `student-muse` | 课表、任务、重要通知和可选的地点配置 | 课表导入、每日简报、截止提醒和天气提示 |
| 学习与计划 | **考试复习助手** `student-exam-planner` | 考试日期、范围和已有安排 | 考试信息汇总、复习重点与按日计划 |
| 学习与计划 | **学业体检** `study-review` | 作业、笔记、复习计划或论文 | 提交前自查、查漏补缺和引用规范检查 |
| 产出与维护 | **海报设计** `daily-task-poster` | 已确认的待办或计划 | 可导出为 PNG 或 JPG 的任务海报，支持离线版式 |
| 产出与维护 | **冗余文件清理** `chat-attachment-tracker` | 指定附件目录和可选的聊天线索 | 重复文件和拟保留路径。确认后可清理副本 |
| 产出与维护 | **Skills 修理所** `skill-workflow-adapter` | 运行日志、本机环境或失败场景 | 路径、依赖和输入格式诊断，附复测步骤及可回退的配置 |

## 运行环境

- 多格式转写、海报和本地脚本一般需要 Python 3.10 或更高版本。包内 `.agents/README.md` 有依赖安装和自检命令。
- 天气属于校园管家。配置地点后可查询天气，暂时无法获取时仍可使用课程、任务和考试功能。
- 定时提醒和读取本机文件取决于所用工具是否支持相应能力。

## 版本历史

| 版本 | 主要变化 |
| --- | --- |
| [v3.0.3](https://github.com/tangxuhang/muse-student-skills/releases/tag/v3.0.3) | 当前完整版。微信缺记录时优先用随包的本机导出。另有从 v3.0.1 和 v3.0.2 升级的补丁。 |
| [v3.0.2](https://github.com/tangxuhang/muse-student-skills/releases/tag/v3.0.2) | 加入首次使用引导、天气重试与缓存，修复海报多行标题、考试范围兼容和事项证据展示。GitHub 发布物为补丁。 |
| [v3.0.1](https://github.com/tangxuhang/muse-student-skills/releases/tag/v3.0.1) | 增加依赖诊断和安装指引，修复抽样批次错位，完善关系报告、消息回查和海报提示。包含 16 个 Skill、中文字体和内置微信导出。 |
| [v3.0](https://github.com/tangxuhang/muse-student-skills/releases/tag/v3.0) | 首个公开的 16 技能完整版，包含微信导出、资料整理、会话分析、学习计划和海报。 |
