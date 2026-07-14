# ADR 0002：使用 PostgreSQL 和 Apache Doris

## 状态

已接受

## 背景

平台需要同时承载业务数据、平台配置和分析型查询。单一数据库难以同时满足事务型管理和高性能分析查询的需求。

## 决策

使用 PostgreSQL 承载业务数据和平台配置，使用 Apache Doris 承载分析型数据仓库。

## 影响

- PostgreSQL 作为 Directus 的主要数据库。
- Doris 作为 Superset 的主要分析数据源。
- DolphinScheduler 负责后续 PostgreSQL 到 Doris 的同步和加工链路。
- DataHub 需要采集 PostgreSQL 和 Doris 的元数据。

## 备选方案

- 仅使用 PostgreSQL：部署简单，但分析查询和大规模聚合能力有限。
- 仅使用 Doris：不适合作为通用业务事务数据库。
- 使用其他 OLAP 引擎：后续可根据性能、生态和运维成本重新评估。
