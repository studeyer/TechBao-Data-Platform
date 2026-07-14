# AGENTS.md

## 项目定位

本项目是一个企业数据平台的开源集成参考实现。

核心原则：

1. 优先使用成熟开源组件。
2. 优先配置和集成，避免重复开发。
3. 不修改上游项目源码，除非存在明确必要性。
4. 各组件保持独立部署，通过 SSO、反向代理、API 和统一数据源集成。
5. 文档必须区分“规划中”“验证中”“已完成”。

## 技术方向

- PostgreSQL：业务数据和配置数据
- Apache Doris：分析数据
- Directus：数据管理与通用 API
- DolphinScheduler：调度与工作流
- Superset：BI
- DataHub：数据目录
- APISIX：API 网关
- Keycloak：SSO
- MinIO：对象存储

## 修改要求

- 修改前先检查现有目录和文档。
- 不随意替换已经确定的组件。
- 新增重大技术决策时创建 ADR。
- 不提交密码、Token、私钥或真实连接信息。
- 示例配置使用 `.env.example`。
- 完成任务后运行必要检查并查看 `git diff`。
