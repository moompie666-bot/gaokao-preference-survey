# 专业方向深度测评

这是一个本地、移动端优先、单 HTML 的高考专业偏好测评工具，面向安徽 2026 物理类考生（530 / 95924 / 物化生）的专业选择辅助讨论。

## 使用方式

1. 用浏览器打开 `tools/preference-survey/index.html`。
2. 确认考生基础信息。
3. 完成 126 道题；浏览器会用 localStorage 自动保存进度。
4. 查看结果页的 9 个区块。
5. 导出：
   - `preferences.generated.json`：供后续脚本导入志愿知识库。
   - `preferences.generated.md`：供家庭讨论和打印。

## 设计原则

- RIASEC/O*NET 兴趣模型为主。
- 能力、职业价值观、工作环境、风险承受共同评分。
- 荣格/认知偏好只做解释，不显示人格类型名。
- 家庭约束用于硬排除、风险提醒、冲突检测。
- 不联网、不登录、不后端、不直接改数据库。

## 功能清单

- 126 题深度测评
- 8 个章节
- localStorage 自动保存
- 移动端优先卡片交互
- 点击排序题，无拖拽依赖
- RIASEC / 能力 / 价值观 / 环境 / 风险 / 认知偏好评分
- 专业方向推荐矩阵
- 家庭约束冲突提醒
- JSON 导出
- Markdown 导出

## 数据隐私

所有答案保存在当前浏览器的 localStorage 中。导出文件由用户手动保存；页面没有任何联网、账号、后端或数据库写入行为。

如需清除本地数据，可在结果页点击“重新开始”，或在浏览器开发者工具中删除 `gaokao.preferenceSurvey.v1`。

## 后续集成

后续可以编写脚本读取 `preferences.generated.json`，更新：

- `candidate/preferences.md`
- `candidate/constraints.md`
- SQLite `candidate_profile` 偏好字段

第一版不自动改数据库，避免误写。
