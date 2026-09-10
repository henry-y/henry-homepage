# 2026 秋季个人课表

- 网页：https://yeyeah.life/timetable/
- 订阅地址：https://yeyeah.life/timetable/calendar.ics
- GitHub：https://github.com/henry-y/henry-homepage/tree/main/timetable

## iPhone 订阅

在 iPhone 上打开网页，点击“订阅到日历”。也可在「日历 → 日历 → 添加日历 → 添加订阅日历」中粘贴订阅地址。选择 iCloud 账户可在同一 Apple 账户的设备间使用。

请使用订阅；下载并一次性导入文件不会持续获取更新。订阅由日历客户端定期刷新，可能存在延迟。日历只包含 116 次已确定时间地点的课程，英语和教学实习待补齐信息。

## 数据和部署

选课系统“已选上列表”于 2026-09-10 核对：11 门、27 学分。2627S1 第 1–18 周课表提供 9 门课程的 116 次具体安排。英语大纲另提供 16 个周二日期，缺钟点和教室；教学实习由各导师安排。

主站已有 GitHub Pages 和 `yeyeah.life` 域名配置，本课表直接使用 `/timetable/` 路径。

**仓库 `_data/timetable.json` 是网页和日历的共同数据来源。** 修改并提交此 JSON 后，现有 GitHub Pages / Jekyll 会同时重建网页和日历，无需额外服务或手工维护两份日程。

编辑地址：https://github.com/henry-y/henry-homepage/edit/main/_data/timetable.json

- `courses` 每行：`[课程号, 名称, 教师, 学分, 类别, 班号]`。
- `events` 每行：`[日期, 课程下标, 开始时间, 结束时间, 教室, 第几次课, 备注, 教学周]`。下标从 0 开始。
- `englishDates` 是英语课尚未补齐时间地点的日期。
- `holidays` 是原表标注的假期。
- `calendarUpdatedUTC` 每次修改日程时更新为 UTC 时间，例如 `20260910T050000Z`。

保持原有课程号、班号、课次稳定，日历 UID 由这些字段构成；调课时修改日期和时间即可，避免产生重复事件。日期使用 `YYYY-MM-DD`，时间使用北京时间 24 小时制 `HH:mm`。

补齐英语时，将它的事件加入 `events` 并删除对应 `englishDates` 条目，同时调整页面中的待补充说明和统计文案。

- `timetable/index.html`：网页模板。
- `timetable/calendar.ics`：日历模板，使用 Asia/Shanghai 时区。
- `_data/timetable.json`：共用数据。

本地交付的 `index.html`、`calendar.ics` 是可直接使用的静态快照；仓库版本使用 Jekyll 模板共享数据。不要用本地快照覆盖仓库模板来维护订阅。

## 核对要点

- 思政课匹配三班：2026-10-16 起，周五 09:00–12:00、C203。
- 教学周依原表为周日—周六，第 1 周实际开课 09-07，第 18 周结束于 2027-01-09。
- 智慧科学导论第 16 次标为期末考核。
- 解析保留 Word 合并单元格，避免节假日导致列错位。已检查日期、周次、次数、教室、假期、思政特殊时间和 18 周桌面/手机课程数量。
- 已排定课程无时间冲突，未纳入英语和实习的冲突检查。临时调课与考试以学院、教师通知为准；本站不自动同步选课系统。
