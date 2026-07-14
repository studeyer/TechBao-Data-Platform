# Docker Compose 部署

本文档用于记录 Docker Compose 方向的部署设计。当前阶段仅建立文档占位，尚未提供可运行的 `docker-compose.yml`。

## 设计原则

- 优先使用官方镜像或社区维护良好的镜像。
- 配置通过环境变量和挂载文件管理。
- 数据卷与配置文件分离。
- 本地默认配置仅用于开发和验证，不直接作为生产配置。

## 规划内容

- 基础网络和命名规范。
- PostgreSQL、Keycloak、MinIO 等基础组件。
- Directus、Superset、DataHub 等应用组件。
- DolphinScheduler、Doris 等数据处理和分析组件。
- APISIX 网关和路由配置。

## 待补充

- 组件版本矩阵。
- 启动顺序和健康检查。
- 默认账号和安全提示。
- 数据卷规划。
- 常见问题排查。
