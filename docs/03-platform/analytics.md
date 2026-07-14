# 数据分析

数据分析规划基于 Apache Superset 实现。

## 目标

- 提供数据集管理、图表和仪表盘能力。
- 支持分析人员进行自助查询和可视化探索。
- 与 Doris 建立主要分析查询链路。

## 规划集成

- Superset 连接 Doris。
- Superset 接入 Keycloak 实现统一登录。
- Superset 元数据进入 DataHub。
- Superset 访问入口可通过 APISIX 或统一门户暴露。

## 待验证事项

- Superset 与 Keycloak 的角色映射方式。
- Superset 连接 Doris 的驱动和 SQL 方言兼容性。
- 仪表盘权限与平台权限的一致性。
