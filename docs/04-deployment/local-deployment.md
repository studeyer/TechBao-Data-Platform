# 本地部署

本文档记录本地部署方向。当前仓库尚未提供可直接运行的完整部署配置。

## 目标

- 用 Docker Compose 建立最小可验证环境。
- 优先验证组件启动、基础配置和关键集成链路。
- 为后续 Kubernetes 部署沉淀配置经验。

## 规划目录

- `compose/`：存放 Docker Compose 编排文件。
- `docker/`：存放镜像构建、初始化配置和组件配置模板。
- `scripts/`：存放本地环境辅助脚本。
- `examples/`：存放示例配置和示例数据。

## 本地环境规划

后续本地环境将逐步包含：

- PostgreSQL
- Directus
- Apache Doris
- Apache DolphinScheduler
- Apache Superset
- DataHub
- Apache APISIX
- Keycloak
- MinIO

## 当前状态

本地部署配置待编写，暂不提供启动命令。
