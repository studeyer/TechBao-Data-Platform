# ADR 0004：评估 DataSphereStudio 作为统一数据开发门户

## 状态

已接受

## 背景

TechBao Data Platform 的目标是形成面向企业数据服务的数据平台产品体系。当前主线采用 PostgreSQL、Doris、DolphinScheduler、Superset、DataHub、APISIX、Keycloak、Directus、MinIO 等成熟开源组件组合。

DataSphereStudio（DSS）提供一站式数据应用开发管理门户、工作空间、工作流和 AppConn 集成机制。DSS 能集成多类数据应用组件，并通过 SSO、组织结构和开发流程规范连接外部系统。这与本项目“先集成，后统一；先能用，再产品化”的路线存在较高相关性。

同时，DSS 生态与当前主线组件存在能力重叠，例如调度、可视化、数据 API、数据模型和血缘能力。如果未经验证直接切换到 DSS 体系，可能增加部署复杂度、组件锁定和产品边界不清晰的风险。

## 决策

当前不全量切换到 DSS，不使用 DSS 替换已经确定的核心组件。

DSS 作为“统一数据开发门户和 AppConn 集成层候选组件”进入评估。评估通过后，再决定其进入核心组件、作为可选增强组件，或仅作为产品设计参考。

## 验证重点

- DSS 基础部署和依赖复杂度。
- DSS 工作空间、工作流和 AppConn 的实际使用成本。
- DSS 与 DolphinScheduler 的调度协同或工作流发布能力。
- DSS 与 Keycloak 的 SSO 集成边界。
- DSS 与 APISIX 统一入口的组合方式。
- DSS 与 Superset、Directus、DataHub 的边界和必要性。

## 影响

- 技术栈中新增 DataSphereStudio 作为候选增强组件，状态为“评估中”。
- 路线图新增 DSS 门户能力评估阶段。
- 后续部署文档需要单独记录 DSS PoC，不把 DSS 混入核心最小验证链路。
- 文档中必须区分 DSS 能力是“规划中”“评估中”“验证中”还是“已完成”。

## 备选方案

- 直接采用 DSS 作为平台底座：统一体验更强，但重叠能力和部署复杂度较高。
- 完全不考虑 DSS：主线更简单，但可能错过 AppConn 和统一开发门户能力。
- 自研统一门户：产品可控性高，但不符合少开发和开源集成优先原则。
