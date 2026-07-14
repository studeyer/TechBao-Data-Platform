# 组件选型

本项目的组件选型遵循成熟度、社区活跃度、标准接口、可替换性和运维成本优先的原则。

## Directus

- 定位：业务数据管理和自动 API。
- 选择原因：提供数据模型管理、权限控制、后台界面和 REST/GraphQL API。
- 集成重点：连接 PostgreSQL，通过 Keycloak 实现 SSO，通过 APISIX 暴露 API。

## PostgreSQL

- 定位：业务数据与平台配置。
- 选择原因：成熟稳定、生态完善、适合承载结构化业务数据。
- 集成重点：作为 Directus 主数据库，也可承载部分组件配置或示例数据。

## Apache Doris

- 定位：分析型数据仓库。
- 选择原因：面向 OLAP 查询场景，适合交互式分析和报表查询。
- 集成重点：承接调度产出的分析数据，供 Superset 查询。

## Apache DolphinScheduler

- 定位：数据开发与任务调度。
- 选择原因：提供工作流编排、依赖管理、调度和任务运行能力。
- 集成重点：编排 PostgreSQL、Doris、MinIO 等组件之间的数据任务。

## Apache Superset

- 定位：数据分析和 BI。
- 选择原因：开源 BI 生态成熟，支持多种数据源和仪表盘能力。
- 集成重点：连接 Doris，接入 Keycloak，向 DataHub 暴露分析资产元数据。

## DataHub

- 定位：数据目录和元数据管理。
- 选择原因：支持多种数据源和 BI 工具的元数据采集，适合建设数据资产目录。
- 集成重点：采集 PostgreSQL、Doris、Superset 等资产信息。

## Apache APISIX

- 定位：API 网关。
- 选择原因：高性能、插件体系成熟，支持路由、鉴权、限流和观测。
- 集成重点：统一 Directus 和后续平台 API 的外部访问入口。

## Keycloak

- 定位：统一认证和 SSO。
- 选择原因：支持 OIDC/SAML，适合统一管理用户、角色和客户端应用。
- 集成重点：为 Directus、Superset、DataHub、APISIX 提供统一身份源。

## MinIO

- 定位：文件和对象存储。
- 选择原因：兼容 S3 API，适合本地和私有化环境中的对象存储需求。
- 集成重点：存放导入导出文件、任务中间文件和后续数据湖相关对象。
