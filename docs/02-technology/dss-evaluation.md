# DataSphereStudio 评估

DataSphereStudio（DSS）当前作为 TechBao Data Platform 的候选增强组件评估。它不替代现有核心组件规划，优先验证其作为统一数据开发门户、工作空间和 AppConn 集成层的价值。

## 评估结论先行

- 当前不全量切换到 DSS 体系。
- 当前不使用 DSS 替换 DolphinScheduler、Superset、DataHub、APISIX、Keycloak。
- 当前把 DSS 定义为“统一数据开发门户候选组件”。
- 评估重点不是 DSS 自身能不能运行，而是它能否低成本集成既有数据应用组件。

## 背景

TechBao Data Platform 的目标是形成面向企业数据服务的数据平台产品体系，能力覆盖数据统一存储、数据资产管理、数据开发与加工、数据分析、数据服务 API、权限管理和开放平台。

现有技术路线以成熟开源组件组合为主：

- PostgreSQL 和 Doris 负责数据存储。
- DolphinScheduler 负责数据开发和调度。
- Superset 负责 BI 分析。
- DataHub 负责数据资产和元数据。
- APISIX 负责 API 网关。
- Keycloak 负责统一认证。
- Directus 负责业务数据管理和通用 API。
- MinIO 负责对象存储。

DSS 的价值在于提供统一数据应用开发门户、工作空间、工作流和 AppConn 集成机制。它适合进入评估，但不应在未验证前替换现有主线。

## DSS 能力定位

DSS 官方定位是“一站式数据应用开发管理门户”。它强调通过 Linkis 和可插拔集成框架接入上层数据应用系统，覆盖数据交换、清洗、分析、质量、可视化、调度和数据输出等数据应用开发过程。

DSS 的 AppConn 是其关键能力。AppConn 定义了外部数据应用系统接入 DSS 的统一前后端集成协议，包含：

- SSO 规范。
- 组织结构规范。
- 开发流程规范。

这说明 DSS 更适合作为“统一数据开发门户和集成工作台”评估，而不是简单作为某个单点组件替代品。

## 与现有组件的关系

| 能力域 | 当前主线组件 | DSS 关系 | 初步策略 |
| --- | --- | --- | --- |
| 数据开发与调度 | DolphinScheduler | DSS 可评估工作流发布、调度协同或 AppConn 集成 | 主线保留，DSS 验证 |
| 数据分析 | Superset | DSS 生态中有 Visualis，但与 Superset 重叠 | 不替换 Superset |
| 数据服务 API | Directus + APISIX | DSS 生态中有 DataApiService，存在能力重叠 | 作为对照验证 |
| 数据资产管理 | DataHub | DSS 生态有数据模型和血缘相关方向，但边界不同 | 不替换 DataHub |
| 统一认证 | Keycloak | DSS 有 SSO 接入规范，但不是统一身份源 | Keycloak 保留 |
| 统一入口 | APISIX | DSS 可作为应用入口之一 | APISIX 保留 |

## 验证目标

### 目标一：门户价值验证

验证 DSS 是否能显著降低数据开发、调度、分析和数据服务之间的切换成本。

验收标准：

- 能说明 DSS 工作空间如何组织项目、用户和数据应用。
- 能说明 DSS 工作流如何串联数据开发任务。
- 能说明 DSS 与现有组件组合后是否减少用户操作复杂度。

### 目标二：AppConn 集成验证

验证 DSS 是否能通过 AppConn 或已有插件集成现有数据应用组件。

优先验证顺序：

1. DSS 与 DolphinScheduler：验证工作流发布、调度协同或插件接入可行性。
2. DSS 与 Keycloak：验证 SSO 接入边界，确认是否能复用统一身份体系。
3. DSS 与 APISIX：验证 DSS 是否可以作为统一入口后的应用之一。
4. DSS 与 Superset：验证是否需要深度集成，还是保持跳转式集成即可。
5. DSS 与 Directus/DataHub：验证是否有必要进入同一工作空间。

验收标准：

- 有可复现部署记录。
- 有最小集成路径说明。
- 有配置项、账号体系、网络访问和权限边界说明。
- 有与现有主线方案的复杂度对比。

### 目标三：重叠能力评估

验证 DSS 生态组件是否会与现有主线组件产生不可接受的重叠。

重点关注：

- DolphinScheduler 与 Schedulis/DSS 工作流的边界。
- Superset 与 Visualis 的边界。
- Directus/APISIX 与 DataApiService 的边界。
- DataHub 与 DSS 数据模型中心、血缘能力的边界。

验收标准：

- 明确哪些能力保留现有组件。
- 明确哪些能力可由 DSS 增强。
- 明确哪些 DSS 生态组件暂不引入。

## PoC 路线

### PoC 0：文档与安装可行性

- 阅读 DSS 官方部署文档。
- 记录依赖组件、版本矩阵、资源要求和部署复杂度。
- 判断是否适合放入本地 Compose 验证环境。

### PoC 1：DSS 基础运行

- 在隔离环境启动 DSS 最小依赖。
- 记录端口、服务、数据库、默认账号和安全注意事项。
- 不接入真实业务数据。

### PoC 2：DSS 与 DolphinScheduler

- 验证 DSS 是否可以接入或发布工作流到 DolphinScheduler。
- 使用示例数据链路作为验证对象。
- 对比直接使用 DolphinScheduler 与通过 DSS 使用 DolphinScheduler 的体验差异。

### PoC 3：DSS 与统一入口和认证

- 验证 DSS 作为 APISIX 后端应用的路由方式。
- 验证 DSS 与 Keycloak 的 SSO 可行性。
- 记录角色、用户、组织和工作空间之间的映射问题。

### PoC 4：产品化判断

根据 PoC 结果选择以下结论之一：

- 纳入核心组件：DSS 成为默认数据开发门户。
- 作为可选增强：DSS 提供给需要统一开发门户的团队。
- 暂不引入：保留当前组件组合，仅吸收 DSS 的产品设计思路。

## 不做事项

- 不为了 DSS 替换已经确定的核心组件。
- 不修改 DSS 或其他上游项目源码。
- 不接入真实连接信息、密码、Token 或私钥。
- 不把 DSS 验证结果提前描述为已完成集成。

## 参考资料

- [DataSphereStudio](https://github.com/WeBankFinTech/DataSphereStudio)
- [DataSphereStudio-Doc](https://github.com/WeBankFinTech/DataSphereStudio-Doc)
