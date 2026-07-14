# 路线图

TechBao Data Platform 的路线图以“先骨架、再验证、后治理”为节奏推进。当前阶段不追求一次性完成所有组件集成，而是逐步沉淀可复现、可替换、可维护的集成方案。

## 阶段一：项目初始化

- 建立 README、贡献指南、变更日志、许可证和代理协作说明。
- 建立产品、技术、平台、部署和 ADR 文档目录。
- 明确开源组件集成优先的总体方向。

## 阶段二：本地最小验证环境

- 编写 Docker Compose 部署草案。
- 验证 PostgreSQL、Directus、Doris、DolphinScheduler、Superset、DataHub、APISIX、Keycloak、MinIO 的基础启动方式。
- 记录端口、账号、数据卷和依赖关系。

## 阶段三：核心集成验证

- 验证 Keycloak 对主要组件的 OIDC/SSO 集成。
- 验证 Directus 连接 PostgreSQL 并通过 APISIX 暴露 API。
- 验证 DolphinScheduler 调度 PostgreSQL 到 Doris 的数据链路。
- 验证 Superset 连接 Doris 进行可视化分析。

## 阶段四：元数据与治理

- 验证 DataHub 采集 PostgreSQL、Doris、Superset 元数据。
- 梳理数据资产命名、标签、责任人和血缘规范。
- 建立基础数据质量和变更管理流程。

## 阶段五：生产化能力

- 设计 Kubernetes 部署方案。
- 补齐监控、日志、告警、备份、恢复和升级策略。
- 梳理安全基线和权限模型。

## 当前状态

当前处于阶段一：项目初始化。
