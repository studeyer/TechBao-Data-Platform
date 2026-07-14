# 路线图

TechBao Data Platform 的路线图以“先骨架、再验证、后治理”为节奏推进。当前阶段不追求一次性完成所有组件集成，而是逐步沉淀可复现、可替换、可维护的集成方案。

## 阶段一：项目初始化

- 建立 README、贡献指南、变更日志、许可证和代理协作说明。
- 建立产品、技术、平台、部署和 ADR 文档目录。
- 明确开源组件集成优先的总体方向。

## 阶段二：主链路最小验证

- 优先验证 PostgreSQL 到 Doris 的数据链路。
- 使用 DolphinScheduler 编排同步、加工和入仓任务。
- 使用 Superset 连接 Doris 构建最小分析看板。
- 形成一条“数据进入、加工、入仓、分析”的可复现链路。

## 阶段三：本地部署与核心集成

- 编写 Docker Compose 部署草案。
- 验证 PostgreSQL、Directus、Doris、DolphinScheduler、Superset、DataHub、APISIX、Keycloak、MinIO 的基础启动方式。
- 记录端口、账号、数据卷和依赖关系。
- 验证 Keycloak 对主要组件的 OIDC/SSO 集成。
- 验证 Directus 连接 PostgreSQL 并通过 APISIX 暴露 API。

## 阶段四：元数据与治理

- 验证 DataHub 采集 PostgreSQL、Doris、Superset 元数据。
- 梳理数据资产命名、标签、责任人和血缘规范。
- 建立基础数据质量和变更管理流程。

## 阶段五：DSS 门户能力评估

- 验证 DataSphereStudio 是否适合作为统一数据开发门户。
- 验证 AppConn 对外部数据应用组件的集成成本和边界。
- 重点验证 DSS 与 DolphinScheduler、Superset、APISIX、Keycloak 的组合可能性。
- 明确 DSS 是进入核心组件、作为可选增强，还是仅吸收产品设计思路。

## 阶段六：生产化能力

- 设计 Kubernetes 部署方案。
- 补齐监控、日志、告警、备份、恢复和升级策略。
- 梳理安全基线和权限模型。

## 当前状态

当前处于阶段一：项目初始化。
