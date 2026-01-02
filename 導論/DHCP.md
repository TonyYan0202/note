## DHCP (Dynamic Host Configuration Protocol，動態主機設定協定)
### 1. 基本概念

- **定義**：自動分配 IP 地址、子網路遮罩、閘道及 DNS 的網路協定。
- **角色**：
    - **Server**：管理者，負責管理 IP 位址池 (Address Pool)。
    - **Client**：需求者，連網設備（如 Windows 電腦、手機）。
- **傳輸細節**：使用 **UDP** 傳輸，伺服器監聽 **Port 67**，客戶端監聽 **Port 68**。

### 2. 運作流程：DORA 四部曲 (核心)

1. **Discovery (發現)**：Client **廣播** (目標 `255.255.255.255`)，「誰是 DHCP 伺服器？我需要 IP！」
2. **Offer (提供)**：Server 回應，「我有 IP `192.168.1.50`，租給你？」
3. **Request (請求)**：Client 回應，「太好了，我要用這個 IP！」
4. **Acknowledgment (確認)**：Server 確認，「成交！這是你的租約時間與設定。」

### 3. 租約機制 (Lease Management)

- **租約時間 (Lease Time)**：Client 會在 **Option 51** 收到剩餘秒數。
- **自動續約計時器**：
    - **T1 (50%)**：Client 以 **Unicast (單播)** 向原伺服器發送 Request。
    - **T2 (87.5%)**：若 T1 失敗，Client 改以 **Broadcast (廣播)** 向全網段求救。
- **過期後果**：租約達 100% 仍未續約成功，Client 必須放棄 IP，若無回應則啟動 **APIPA (169.254.x.x)**。

### 4. 實務觀察與問題排除 (進階重點)

#### 廣播風暴 (Broadcast Storm)
- **成因**：通常由 Layer 2 **物理迴路 (Loop)** 引起，而非 DHCP 本身。
- **影響**：DHCP Discovery 封包被無限複製，導致伺服器 CPU 癱瘓或頻寬塞滿。
- **應急手段**：將 Client 改為 **手動靜態 IP** 可跳過 DORA 流程，暫時恢復連線。

## 5. 常用指令 (Windows)

- `ipconfig /all`：查看租約起迄時間。
- `ipconfig /release`：主動歸還 IP，終止租約。
- `ipconfig /renew`：強制重新發起 DHCP 流程。