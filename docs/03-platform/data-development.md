# 数据开发

数据开发规划基于 Apache DolphinScheduler 实现。

## 目标

- 提供数据任务编排能力。
- 支持定时调度、依赖编排和失败重试。
- 编排 PostgreSQL、Doris、MinIO 等组件之间的数据任务。

## 规划集成

- 使用 DolphinScheduler 管理数据同步和加工工作流。
- 将 PostgreSQL 数据加工后写入 Doris。
- 使用 MinIO 存储任务中间文件或交换文件。
- 后续将任务、表和血缘信息纳入 DataHub。

## 待验证事项

- DolphinScheduler 的元数据库选型与部署方式。
- PostgreSQL 到 Doris 的同步工具和任务类型。
- 任务日志、告警和权限边界。
