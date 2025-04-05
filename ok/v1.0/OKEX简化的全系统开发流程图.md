Here is a simple flow chart:

```mermaid
graph TD
    A[云基础设施] --> B[数据采集系统]
    A --> C[监控报警系统]
    
    subgraph 基础设施
        A1[资源编排] --> A2[网络优化]
        A2 --> A3[IP池管理]
    end
    
    subgraph 数据层
        B1[行情获取] --> B2[K线合成]
        B2 --> B3[数据清洗]
        B3 --> B4[实时分发]
    end
    
    subgraph 核心系统
        C1[策略模拟] --> C2[风险控制]
        C2 --> C3[订单执行]
        C3 --> C4[仓位管理]
    end
    
    subgraph 监控层
        D1[心跳检测] --> D2[异常恢复]
        D2 --> D3[报警通知]
    end
    
    B4 -->|行情数据| C1
    C4 -->|交易信号| 交易所API
    D1 -.->|监控| A
    D1 -.->|监控| B
    D1 -.->|监控| C
    
    style A fill:#f9f,stroke:#333
    style B fill:#cff,stroke:#333
    style C fill:#fcc,stroke:#333
    style D1 fill:#cfc,stroke:#333
```
