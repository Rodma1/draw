# draw

个人 draw.io 图库。所有图均为 `.drawio` 原生格式，用 [draw.io 桌面版](https://github.com/jgraph/drawio-desktop/releases) 或 [app.diagrams.net](https://app.diagrams.net/) 直接打开编辑。

## 目录约定

- 新图按主题放入对应子目录，不再平铺在根目录
- 文件名用英文小写加连字符，如 `agent-runtime.drawio`
- 只保留 `.drawio` 一种格式（其本身即 XML，无需另存 `.xml`）

```
draw/
├── ai/            AI、Agent、大模型相关
├── network/       网络工程师笔记配图
└── (根目录)        历史遗留图，暂未归档
```

## ai/

| 文件 | 内容 |
|---|---|
| [agent-runtime.drawio](ai/agent-runtime.drawio) | Agent Runtime 运行机制：LLM 决策层、工具层、记忆层、调度循环四块结构；重点用虚线 `tool_call` 与实线 `observation` 区分「模型只下单、工具真干活」 |
| [program-workflow-agent.drawio](ai/program-workflow-agent.drawio) | 三栏对比：普通程序（串行无分支）、Workflow 编排（人画图、路径固定）、Agent（闭环、模型定路）。结论句：下一步谁说了算 |
| [react-loop.drawio](ai/react-loop.drawio) | ReAct 调度循环：Thought → Action → Observation 顺时针四拍闭环，每圈结果 append 进 messages；两个出口——「还有工具要调吗」为否则输出答案，`steps > MAX_STEPS` 触发红色熔断强制中断 |
| [three-patterns.drawio](ai/three-patterns.drawio) | 三种主流模式对比：ReAct（四拍环、闭环边探边试）、Plan-Execute（计划清单 + 线性执行）、Multi-Agent（Planner/Executor/Reviewer 三角互检）。每栏附代价与适用场景 |

## 根目录（历史图）

AI 相关：

| 文件 | 说明 |
|---|---|
| [ai.drawio](ai.drawio) | AI 相关 |
| [ai文章.drawio](ai文章.drawio) | AI 文章相关 |
| [ai模型.drawio](ai模型.drawio) | AI 模型 |
| [ai模型2.drawio](ai模型2.drawio) | AI 模型（二） |

架构与微服务：

| 文件 | 说明 |
|---|---|
| [微服务化.drawio](微服务化.drawio) | 微服务化 |
| [公共服务.drawio](公共服务.drawio) | 公共服务 |
| [company.drawio](company.drawio) | 公司架构 |
| [cas跨域单点登录.drawio](cas跨域单点登录.drawio) | CAS 跨域单点登录 |
| [navigate.drawio](navigate.drawio) | 导航 |

中间件与存储：

| 文件 | 说明 |
|---|---|
| [redis分布式锁.drawio](redis分布式锁.drawio) | Redis 分布式锁、看门狗 |
| [netty.drawio](netty.drawio) | Netty |
| [es后台管理.drawio](es后台管理.drawio) | ES 后台管理 |
| [es开发流程.drawio](es开发流程.drawio) | ES 开发流程 |

基础与网络：

| 文件 | 说明 |
|---|---|
| [网络知识.drawio](网络知识.drawio) | 网络知识 |
| [what is https.drawio](what%20is%20https.drawio) | HTTPS 原理 |
| [java图片.drawio](java图片.drawio) | Java 相关 |

业务相关：

| 文件 | 说明 |
|---|---|
| [hnzj.drawio](hnzj.drawio) | 海南槟榔（hnzj）业务 |
| [dh.drawio](dh.drawio) | dh |

## network/

| 文件 | 内容 |
|---|---|
| [115-port-security.drawio](network/115-port-security.drawio) | 端口安全完整配图（4 页）：①三种 MAC 绑定方式对比——dynamic 掉电就丢 / static 手工最稳 / sticky 折中省事；②MAC 泛洪攻击原理——表塞满→查不到目的 MAC→未知单播泛洪→交换机退化成 HUB；③实验拓扑——一台交换机两个口两套策略；④三种违规动作——protect 静默丢弃 / restrict 告警留证 / shutdown 直接断网，且华为默认就是 shutdown。 |
| [116-ipsec-vpn.drawio](network/116-ipsec-vpn.drawio) | IPsec VPN 全套配图（3 页）：①四个组件关系——ACL 圈流量 / 安全提议定算法 / IKE 协商密钥 / 策略做组装 / 接口才生效；②IKE 两阶段协商——阶段1 建 IKE SA，阶段2 在已加密通道里建 IPsec SA；③实验拓扑——总部 R1 与分支 R2 跨 Internet，物理走公网逻辑走加密隧道。含原 PDF 资料 3 处勘误（IKE 版本命令、R2 前缀写错、注释与命令矛盾）。算法用 sha1（eNSP 老设备不支持 sha2-256）。 |
| [117-switch-perf.drawio](network/117-switch-perf.drawio) | 交换机性能参数计算（2 页，纯理论无需实验）：①以太网帧在线路上的实际占用——前导码8B + 最小帧64B + 帧间隙12B = 84B，附「为什么按84不按64算」的易错点；②全双工为什么要乘2——收发两条独立通道，N 个千兆口占背板 N×2 Gbps。核心考点：单口千兆 1.488 Mpps 的推导、整机包转发率与背板带宽公式。 |
