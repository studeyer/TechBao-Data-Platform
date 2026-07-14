# 统一认证

统一认证规划基于 Keycloak 实现。

## 目标

- 提供统一用户、角色、客户端和认证流程。
- 支持 OIDC/SAML 单点登录。
- 降低各组件独立维护账号体系的成本。

## 规划集成

- Directus 接入 Keycloak。
- Superset 接入 Keycloak。
- DataHub 接入 Keycloak。
- APISIX 与 Keycloak 协同进行 API 认证。

## 权限方向

- 平台角色：平台管理员、数据开发、数据分析、数据治理、应用开发。
- 组件角色：保留组件自身权限模型，通过映射逐步统一。
- API 权限：由 APISIX 和后端组件共同控制。

## 待验证事项

- 各组件 OIDC 支持能力和配置差异。
- 角色映射和用户同步策略。
- Token 生命周期和刷新策略。
- 本地环境与生产环境的 Realm 配置管理方式。
