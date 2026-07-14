# 数据目录

数据目录规划基于 DataHub 实现。

## 目标

- 管理数据资产清单。
- 展示表、字段、指标、仪表盘等元数据。
- 支持标签、责任人、血缘和数据域管理。

## 规划集成

- 采集 PostgreSQL 元数据。
- 采集 Doris 元数据。
- 采集 Superset 仪表盘和数据集元数据。
- 后续补充 DolphinScheduler 任务血缘。

## 待验证事项

- DataHub 各 source 的版本兼容性。
- Doris 元数据采集方式。
- Superset 元数据采集权限。
- 责任人、标签和数据域的维护流程。
