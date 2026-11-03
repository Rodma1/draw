# draw

个人 draw.io 图库。所有图均为 `.drawio` 原生格式，用 [draw.io 桌面版](https://github.com/jgraph/drawio-desktop/releases) 或 [app.diagrams.net](https://app.diagrams.net/) 直接打开编辑。

## 目录约定

- 新图按主题放入对应子目录，不再平铺在根目录
- 文件名用英文小写加连字符，如 `agent-runtime.drawio`
- 只保留 `.drawio` 一种格式（其本身即 XML，无需另存 `.xml`）

```
draw/
├── ai/            AI、Agent、大模型相关
└── (根目录)        历史遗留图，暂未归档
```

## ai/

| 文件 | 内容 |
|---|---|
| [agent-runtime.drawio](ai/agent-runtime.drawio) | Agent Runtime 运行机制：LLM 决策层、工具层、记忆层、调度循环四块结构；重点用虚线 `tool_call` 与实线 `observation` 区分「模型只下单、工具真干活」 |
| [program-workflow-agent.drawio](ai/program-workflow-agent.drawio) | 三栏对比：普通程序（串行无分支）、Workflow 编排（人画图、路径固定）、Agent（闭环、模型定路）。结论句：下一步谁说了算 |

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
