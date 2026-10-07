# MCFSO

> Minecraft 服务器生态的开源组织 —— 从客户端工具到内核级基础设施。

MCFSO 致力于构建 Minecraft 服务器管理的完整工具链，并探索底层系统软件的实现。我们的项目横跨 Flutter 应用、Rust 原生库、Go 守护进程，以及从零编写的 x86_64 微内核。

---

## 主要项目

### IriX —— Minecraft 服务器管理工具

跨平台 Minecraft 服务器管理工具。Flutter 构建 UI，Rust 提供高性能底层支持（压缩、下载、HTTP、数据库、编排、NBT、日志），覆盖实例管理、核心下载、插件市场、备份压缩、文件管理、内网穿透、节点与集群编排、远程数据库、NBT 编辑与 AI 助手等完整工作流。

- **仓库**：`IriX`
- **技术栈**：Flutter + Rust
- **许可**：MIT

### IriX Node Daemon —— 本地节点守护进程

IriX 客户端「节点」类型中的本地节点守护进程，Go 语言实现。与 MCSManager 面板提供同一风格的 HTTP API，IriX 客户端可用同一套代码同时管理 MCSM 节点与本节点。

- **仓库**：`irix-node`
- **技术栈**：Go（标准库为主，账户管理引入 SQLite/MySQL/PostgreSQL/Redis 驱动）
- **特性**：多平台部署、加密保险库、高并发调优、容器支持
- **许可**：MIT

### FEKernel —— x86_64 微内核

从零实现的 x86_64 操作系统**内核（微内核）**。内核只提供机制（内存、调度、IPC、对象、中断、能力），设备驱动、文件系统、协议栈、shell 全部是内核之外的用户态服务。

- **仓库**：`FEKernel`
- **规模**：约 2.2 万行 C/ASM，约 50 个系统调用，M0–M19 里程碑已完成
- **验证**：QEMU + WHPX 与 VirtualBox 7.2 (UEFI) 双环境实测
- **许可**：0BSD

---

## 技术方向

| 领域 | 技术 |
|------|------|
| 跨平台 UI | Flutter 3.x, Provider |
| 原生底层 | Rust（FFI 动态库：压缩、下载、HTTP、数据库、编排、NBT） |
| 守护进程 | Go（标准库为主，SQLite/MySQL/PostgreSQL/Redis） |
| 系统内核 | C / ASM（x86_64 微内核，Limine 引导） |
| 网络 | ureq + rustls, WebSocket |
| 存储 | SQLite, Milvus（向量）, 远程数据库 |
| 编排 | K8s 风格期望状态对账、弹性扩缩容、跨机迁移 |

---

## 参与贡献

1. Fork 你感兴趣的仓库
2. 创建特性分支：`git checkout -b feature/your-feature`
3. 提交更改：`git commit -m "feat: ..."`
4. 推送并创建 Pull Request

也欢迎通过 Issue 反馈问题或提出建议。

---

## 联系我们

- GitHub 组织：[https://github.com/MCFSO](https://github.com/MCFSO)
- 各项目文档请参见对应仓库的 `docs/` 目录

---

## 许可

各项目采用各自仓库中声明的许可证：

- **IriX**：MIT License
- **FEKernel**：0BSD（BSD Zero Clause License）
- **IriX Node Daemon**：MIT License

---

感谢所有贡献者的支持。
