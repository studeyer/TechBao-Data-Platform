# 集成架构

集成架构以标准协议为主，减少定制开发。

## 认证集成

- Keycloak 作为统一身份提供方。
- Directus、Superset、DataHub 优先通过 OIDC 接入。
- APISIX 可通过插件与 Keycloak 协同完成 API 认证。
- 角色和权限映射需要在后续验证阶段明确。

## API 集成

- APISIX 作为统一 API 入口。
- Directus 自动生成的 API 可通过 APISIX 暴露。
- 后续平台管理 API 或适配 API 也应通过 APISIX 统一治理。

## 数据集成

- PostgreSQL 承载业务数据和部分平台配置。
- DolphinScheduler 编排数据同步、加工和入仓任务。
- Doris 承载分析型数据集市和报表查询。
- Superset 通过 SQL/JDBC 连接 Doris。

## 元数据集成

- DataHub 负责采集 PostgreSQL、Doris、Superset 等元数据。
- 元数据采集方式优先使用 DataHub 官方支持的 source 或 connector。
- 血缘、标签、责任人和数据域规范需要在后续治理阶段补充。

## 文件集成

- MinIO 作为 S3 兼容对象存储。
- 适合承载导入导出文件、调度任务中间文件和分析附件。
- 文件生命周期、安全策略和桶规范待后续定义。

## DSS 门户集成评估

- DataSphereStudio 当前作为候选增强组件评估，不作为核心必选底座。
- 评估重点是 DSS 的 AppConn 能力是否能把外部数据应用组件纳入统一开发流程。
- 第一阶段不替换 DolphinScheduler、Superset、DataHub、APISIX、Keycloak。
- 优先验证 DSS 与 DolphinScheduler 的工作流发布或调度协同能力。
- 其次验证 DSS 与统一认证、统一入口、分析工具和数据服务能力的组合边界。

## 当前状态

以上内容为规划中的集成架构，尚未完成可复现验证。
