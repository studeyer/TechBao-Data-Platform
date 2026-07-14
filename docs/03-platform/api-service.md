# API 服务

API 服务规划基于 Directus 和 Apache APISIX 实现。

## 目标

- 统一管理 API 入口。
- 支持路由、鉴权、限流、审计和观测。
- 将 Directus 自动 API 作为第一类平台 API 能力。

## 规划集成

- Directus 生成业务数据 API。
- APISIX 统一暴露 Directus API。
- APISIX 与 Keycloak 协同完成认证。
- 后续可接入更多平台适配 API。

## 待验证事项

- APISIX OIDC/JWT 插件配置。
- API 路由命名规范。
- API 版本管理策略。
- API 日志和调用审计方案。
