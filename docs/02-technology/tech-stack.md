# 技术栈

本项目优先使用成熟开源组件，避免重复建设基础平台能力。

## 核心组件

| 层级 | 组件 | 用途 |
| --- | --- | --- |
| 统一认证 | Keycloak | OIDC/SAML、用户、角色、SSO |
| API 网关 | Apache APISIX | 路由、鉴权、限流、观测入口 |
| 业务数据管理 | Directus | 数据模型管理、权限、自动 API |
| 业务数据库 | PostgreSQL | 业务数据和平台配置 |
| 分析型数仓 | Apache Doris | OLAP 查询、明细和汇总分析 |
| 数据开发 | Apache DolphinScheduler | 工作流编排、任务调度 |
| 数据分析 | Apache Superset | BI、报表、仪表盘 |
| 数据目录 | DataHub | 元数据、血缘、标签、责任人 |
| 对象存储 | MinIO | S3 兼容对象存储 |

## 标准协议

- OIDC/SAML：统一认证和单点登录。
- REST/OpenAPI：业务 API 和平台 API。
- JDBC/SQL：数据库连接和查询。
- S3 API：对象存储访问。
- HTTP/gRPC：组件服务通信。

## 部署技术

- Docker Compose：用于本地验证和最小环境编排。
- Kubernetes：用于后续测试环境和生产环境部署参考。
- Helm/Kustomize：后续根据组件生态和维护成本选择。

## 当前约束

当前仓库尚未锁定具体组件版本。组件版本应在本地部署草案阶段结合兼容性、镜像可用性和安全修复状态确定。
