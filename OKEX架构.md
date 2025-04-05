Here is a simple flow chart:

```mermaid
graph TD
    A[中心WS服务器] -->|25ms| B[模拟计算集群]
    A -->|18ms| C[实盘交易节点]
    
    subgraph 数据层
        D1(WS行情服务器)
        D2(K线采集节点x10)
        D3(全量备份节点x5)
    end
    
    subgraph 计算层
        E1(速率模拟x32)
        E2(预期盈利x10)
        E3[混合部署节点]
    end
    
    subgraph 交易层
        F1(账户A实盘x2)
        F2(账户B实盘x2)
    end
    
    subgraph 监控层
        G1[健康检查]
        G2[自动恢复]
        G3[飞书报警]
    end
    
    H[(中心数据库)]
    
    D1 -->|分发| A
    D2 -->|HTTP| A
    D3 -->|冗余| A
    B -->|信号| C
    C -->|订单| 币安API
    G1 -.->|心跳检测| 所有节点
    H <--> 所有节点
```
