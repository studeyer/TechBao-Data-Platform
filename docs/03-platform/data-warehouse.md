# 数据仓库

分析型数据仓库规划基于 Apache Doris 实现。

## 目标

- 承载面向分析的明细数据和汇总数据。
- 支持 BI 报表和交互式查询。
- 与数据开发、数据目录和 BI 工具形成基础链路。

## 规划集成

- DolphinScheduler 负责将数据写入 Doris。
- Superset 连接 Doris 进行可视化分析。
- DataHub 采集 Doris 元数据。

## 建模方向

- 贴源层：保留从业务系统同步的数据。
- 明细层：清洗、标准化后的分析明细数据。
- 汇总层：面向主题和指标的聚合数据。
- 服务层：面向报表、看板和 API 的查询模型。

## 待验证事项

- Doris 部署拓扑和资源配置。
- PostgreSQL 到 Doris 的数据同步方式。
- Doris 与 Superset、DataHub 的兼容性。
