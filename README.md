# ih-accel  
Hypixel proxy (accelerator) that works on L4-5.  
Hyp加速器节点程序  

## Why iH Accel

> iH Accel真正的 L4 级加速器，不是一个普通的转发方案（比如说ZBProxy），谁用谁知道，用过都说好。

## 🚀 部署方式

- **Windows**：运行 `hyp.exe`  
- **Linux**：运行 `./hyp`

⚠️ 默认监听 `25565` 端口，请确保防火墙已关闭或放行该端口。

---

## ✨ 核心技术一览

```mermaid
graph TD
  A[L4 Socket层优化] -->|Naggle合并| B[ANaggle]
  A -->|TCP空包维持| C[NeverSleep]
  A -->|流控识别| D[QoS调度]

  E[L5 会话层增强] -->|MC头透传| F[HeaderMod]
  E -->|AnyCast劫持优化| G[EveryCast]

  B --> Z[低延迟连接]
  C --> Z
  D --> Z
  F --> Z
  G --> Z
````

---

## 🛠 技术要点速览

### ANaggle（L4）

* 自适应 TCP 聚合，兼容 Netty 拆包逻辑
* PPS 降低 > **30%**，输入延迟下降明显

### NeverSleep（L4）

* 智能空包，维持 ISP 连接优先级

### QoS 控制（L4）

* 实时应对 PVP 场景的延迟爆发

### HeaderMod（L5）

* 透明化处理，兼容正版登录全流程

### EveryCast（L5）

* 替代 DNS AnyCast 路由，动态测速选线
* 降低断流概率




## 📬 联系我们

如有 Bug / 合作 / 定制优化需求，欢迎通过issue联系我们。
