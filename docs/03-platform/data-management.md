# 业务数据管理

业务数据管理规划基于 Directus 和 PostgreSQL 实现。

## 目标

- 提供通用数据模型管理能力。
- 提供后台管理界面。
- 提供自动生成的 REST/GraphQL API。
- 支持权限控制和审计基础能力。

## 规划集成

- Directus 连接 PostgreSQL。
- Directus 接入 Keycloak 实现统一登录。
- Directus API 通过 APISIX 暴露。
- 关键业务表的元数据后续进入 DataHub。

## 待验证事项

- Directus 与 Keycloak 的 OIDC 配置方式。
- Directus 权限模型与平台角色的映射关系。
- APISIX 对 Directus API 的认证和限流策略。
