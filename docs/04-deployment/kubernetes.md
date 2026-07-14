# Kubernetes 部署

本文档用于记录 Kubernetes 部署方向。当前阶段尚未提供 Kubernetes 清单、Helm Chart 或 Kustomize 配置。

## 目标

- 将本地验证过的组件集成方式迁移到 Kubernetes。
- 支持测试环境部署。
- 为生产环境提供参考架构和配置基线。

## 设计方向

- 优先复用各组件官方 Helm Chart。
- 使用 Secret 和 ConfigMap 管理配置。
- 使用 Ingress 或 APISIX 统一入口。
- 使用持久化存储承载数据库、仓库和对象存储数据。
- 通过命名空间隔离平台组件。

## 待验证事项

- 各组件 Helm Chart 的稳定性和兼容性。
- 存储类、资源配额和调度策略。
- Keycloak Realm 配置的 GitOps 管理方式。
- APISIX 在集群内外的部署拓扑。
- Doris、DataHub 等组件的资源需求和扩缩容策略。
