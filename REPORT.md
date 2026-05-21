# Vera Rubin VR200 NVL72 供應鏈深度報告

> **時點：** 2026-05-21 · **基底：** Morgan Stanley 估算的 VR200 NVL72 BOM (~$7.8M/櫃)
>
> **Confidence tiers:** 🟢H 高（多源公開法人/媒體確認） · 🟡M 中（單一來源/法人估值） · 🟠L 低（推論/業界傳聞） · ❓ 資料不足
>
> ⚠️ **本報告為資訊整理，非投資建議。**

---

## 0 · 機櫃骨架概覽

| 項目 | GB300 | VR200 | Δ | 備註 |
|---|---|---|---|---|
| 單櫃 BOM | $4.0M | **$7.8M** | +95% | 🟢H Morgan Stanley |
| GPU 數 | 72 (B300) | 72 (Rubin) | — | 每 tray 4 GPU + 2 Vera CPU |
| GPU TDP | ~1,400W | **2,300W** (主流) / 1,800W | — | 🟡M 經濟日報引法人 |
| HBM 規格 | HBM3e | **HBM4** | — | 每 GPU 288GB |
| 機櫃功耗 | ~140kW | ~200kW+ | — | 全液冷、無風扇運算托盤 |
| ABF 載板層數 | 14L (B200) | **18L** | +29% | 🟢H 大摩研報 |
| 主運算板 PCB 層數 | 22L | **26L** | +18% | 🟡M IEK |
| PCB 材料 | M7/M8 | **M8.5** | 升級 | 🟡M IEK |

---

## 1 · GPU — 🇺🇸 NVDA 獨佔，台廠吃封測

| 公司 | 代號 | 角色 | VR200 入列 | 估計份額 | 排名 | 來源 |
|---|---|---|---|---|---|---|
| **NVIDIA** | NVDA US | Rubin GPU 設計 + 定價 | ✅ | **100%** 🟢H | #1 唯一 | 官方 |
| **TSMC** | 2330 / TSM | N3P 製程 + CoWoS-L 封裝 | ✅ | **~100%** 🟢H | #1 | 官方 |
| **Amkor / 日月光** | 3711 | 後段封測（次要） | 🟡 | ❓ | — | 業界傳 |

**單機含量：** GPU $3.96M（51% of BOM，+57% vs GB300）  
**下修風險：** Rubin Ultra 從 4-die 變 2-die（2027），封裝難度與 ASP 可能下修。

---

## 2 · CPU + LPDDR5X — Vera CPU + 台/韓/美三家分

| 公司 | 代號 | 角色 | VR200 入列 | 估計份額 | 排名 | 來源 |
|---|---|---|---|---|---|---|
| **NVIDIA** | NVDA | Vera CPU (Arm 架構) 設計 | ✅ | 100% 設計 🟢H | #1 | 官方 CES 2026 |
| **TSMC** | 2330 | Vera CPU 製造 | ✅ | ~100% 🟢H | #1 | 業界共識 |
| **南亞科** | 2408 | LPDDR5X (Vera CPU 主記憶體) | ✅ | ❓ 尚未公布 | 🟠 切入新供應鏈 | Threads/業界傳 |
| **SK Hynix** | 000660 KS | LPDDR5X | ✅ | ❓ | — | — |
| **Samsung** | 005930 KS | LPDDR5X | ✅ | ❓ | — | — |

**單機含量：** CPU $180K（與 GB300 持平，+0%）；LPDDR5X 含於 Memory 總額  
**新故事：** **南亞科** 首次切入輝達 AI 平台供應鏈 ⭐  
**下修風險：** Vera CPU 採自研 Arm，**Intel/AMD 出局**。

---

## 3 · HBM4 Memory — 韓系雙雄獨吃，台廠零份額

| 公司 | 代號 | 角色 | VR200 入列 | 估計份額 | 排名 | 來源 |
|---|---|---|---|---|---|---|
| **SK Hynix** | 000660 KS | HBM4 主供 | ✅ | **~70%** 🟢H | #1 | letsdatascience.com / techpowerup |
| **Samsung** | 005930 KS | HBM4 次供 | ✅ | **~30%** 🟢H | #2 | 同上 |
| **Micron** | MU US | HBM4 | ❌ **未入列** 🟢H | 0% | — | TrendForce |

**單機含量：** Memory 總額 **$2.0M（26% of BOM，+435% 暴漲）**  
**重點：** 每 Rubin GPU 搭 288GB HBM4，72 GPU × 288GB = 20.7TB/櫃  
**下修風險：** SDxCentral 報導 SK Hynix/Samsung 22 TB/s 規格 miss → Nvidia 已下修 HBM4 spec，Rubin 出貨從 29% → 22%（2026）。

---

## 4 · NVLink Switch / Networking — NVDA 自家 + AVGO/MRVL 邊緣

NVIDIA 在 VR200 把網通晶片**全部自家設計**，台廠主要吃封測 + 板廠 + 連接器。

| 晶片 | 設計 | 製造 | 封測台廠 | 板廠台廠 |
|---|---|---|---|---|
| **NVLink 6 Switch** | NVDA 🟢H | TSMC | ❓ | 欣興/南電 (ABF) |
| **ConnectX-9 SuperNIC** | NVDA 🟢H | TSMC | ❓ | 同上 |
| **BlueField-4 DPU** | NVDA 🟢H | TSMC | ❓ | 同上 |
| **Spectrum-X Ethernet (CPO)** | NVDA 🟢H | TSMC + 矽光子 | ❓ | 玉晶光？❓ |
| **Quantum-X InfiniBand (CPO)** | NVDA 🟢H | TSMC | ❓ | 同上 |

| 周邊受惠美股 | 代號 | 角色 |
|---|---|---|
| **Broadcom** | AVGO | 高速 SerDes IP（部分授權給 NVDA） 🟠L |
| **Marvell** | MRVL | AEC retimer / 光通訊 DSP 🟢H |
| **Astera Labs** | ALAB | AEC retimer 主供（GB200/300，VR200 延續）🟢H |
| **Credo** | CRDO | AEC 第二供 🟡M |

**單機含量：** Networking chips $576K（+121% vs GB300）+ NVLink Switch $144K（+122%）  
**下修風險：** CPO（光通訊）2027+ 才大量導入，VR200 仍以**銅纜 AEC 為主**，光模組廠（旭光、聯亞）含量有限。

---

## 5 · 散熱 — 🇹🇼 台廠最大金礦線

> 「VR 世代均熱片用量 +3x、水冷板/分歧管/快接頭 +50% 以上」— IEK / 工商時報

| 公司 | 代號 | 角色 | VR200 入列 | 估計份額 | 排名 | 來源 |
|---|---|---|---|---|---|---|
| **奇鋐** | 3017 | 水冷板主供、機殼、伺服器導軌、Manifold | ✅ 🟢H | **~50%** GB300 水冷板 🟡M | **#1** | 工商時報 / wantrich |
| **雙鴻** | 3324 | 水冷板第二供、AWS Trainium 客製 | ✅ 🟢H | ~30% 🟠L | **#2** | 工商時報 |
| **健策** | 3653 | 均熱片（量 +3x）、MCL 冷板陣營領頭 | ✅ 🟢H | ❓ | **#1 均熱片** | 工商時報 |
| **富世達** | 6805 | 快接頭（QDC），LPX 機櫃首選 | ✅ 🟢H | ❓ 但與奇鋐並列首選 | **#1 QDC** | 工商時報 / IEK |
| **建準** | 2421 | 風扇 → 轉型液冷 | 🟡 部分 | ❓ | — | 工商時報 |
| **高力** | 8996 | 熱交換器（CDU 級） | 🟡 部分 | ❓ | — | facebook/pocketstock |
| **尼得科超眾** | 6230 | 散熱模組 | 🟡 部分 | ❓ | — | — |

**單機含量：** Cooling $72K（+12% vs GB300，但**量 +3x**，Total ASP 大增）  
**法人 EPS 預估：**
- 奇鋐 2026E EPS 上看 95 元 🟡M (FTNN)
- 雙鴻 2026E EPS 56.2 / 2027E 71.65（高盛）；外資估 54 / 68（花旗）🟢H

**新故事：** 富世達首次以「快接頭」獨立進入主要供應鏈 ⭐  
**下修風險：** 黃仁勳 CES 2026 提「資料中心不再需要水冷式冷卻機」一度造成水冷三雄股價急殺，但實際指的是**外部 chiller 不是機櫃內水冷**，台廠水冷板 ASP 仍維持。MCL（健策）vs MCCP（奇鋐/雙鴻）路線之爭，VR200 採 MCCP，**Rubin Ultra 才可能採 MCL**。

---

## 6 · 電源 — HVDC 大改架構，台達電獨大

> 「VR200 大規模導入 HVDC（高壓直流），2026 Q3 出貨」— IEK

| 公司 | 代號 | 角色 | VR200 入列 | 估計份額 | 排名 | 來源 |
|---|---|---|---|---|---|---|
| **台達電** | 2308 | HVDC 機櫃電源主供、PSU、BBU | ✅ 🟢H | **~50-60%** 🟡M | **#1** | IEK / 商周 |
| **光寶科** | 2301 | PSU 第二供 | ✅ 🟡M | ❓ | #2 | 業界傳 |
| **群電** | 6412 | PSU | 🟡 | ❓ | — | — |
| **康舒** | 6282 | PSU | 🟡 | ❓ | — | — |

**單機含量：** Power supply $76K（+32%）+ PSU 規格升 50~55% → ASP 提升  
**下修風險：** HVDC 標準化進度，2026 Q3 出貨晚於原 H1 預期。

---

## 7 · PCB（高層數運算板 + Midplane）— 老將 + 新故事並存

> 主運算板 22L → 26L、材料升 M8.5、新增 midplane（中介板）連結 tray PCB

| 公司 | 代號 | 角色 | VR200 入列 | 估計份額 | 排名 | 來源 |
|---|---|---|---|---|---|---|
| **欣興** | 3037 | 高層數運算板（延續 GB200/300） | ✅ 🟢H | ❓ 主供 | **#1** | IEK / Yahoo |
| **金像電** | 2368 | GPU baseboard 高層 PCB | ✅ 🟢H | ❓ | #2 | 業界 |
| **健鼎** | 3044 | 高層數 PCB | ✅ 🟡M | ❓ | — | 業界 |
| **臻鼎-KY** | 4958 | **首度入列 VR200 PCB 供應** ⭐ | ✅ 🟢H | ❓ | 新進 | IEK / Yahoo |
| **定穎投控** | 3715 | **首度入列** ⭐ | ✅ 🟢H | ❓ | 新進 | IEK / Yahoo |
| **台燿** | 6274 | M8.5 銅箔基板 | 🟡 | ❓ | — | — |
| **聯茂** | 6213 | 銅箔基板 | 🟡 | ❓ | — | — |

**單機含量：** PCB $116.7K（+233%）  
**新故事：** **臻鼎、定穎首次切入 VR200，是 BOM 表的最大彈性票** ⭐⭐  
**下修風險：** Rubin Ultra 從 4-die → 2-die，PCB 含量單機可能下修。

---

## 8 · ABF 載板 — 雙雄 + 日系競爭

> 全球前五大廠（欣興/南電/Ibiden/Shinko/AT&S）控制 60-74% 全球產能，無單一廠超過 18%

| 公司 | 代號 | 角色 | VR200 入列 | 估計份額（全球 ABF） | 排名 | 來源 |
|---|---|---|---|---|---|---|
| **欣興** | 3037 | ABF 雙雄之一 | ✅ 🟢H | **~18%（全球）** 🟢H | **#1 全球** | mordorintelligence / fspinvest |
| **南電** | 8046 | ABF 雙雄之二 | ✅ 🟢H | ~14% 🟢H | #3 | 同上 |
| **景碩** | 3189 | ABF（中低階） | 🟡 | ~5-8% | — | 業界 |
| **Ibiden** | 4062 JP | 日系老牌 | 部分 NVDA 訂單 🟢H | ~17% | #2 | 同上 |
| **Shinko** | 6967 JP | 日系 | 部分 | ~10% | #4 | 同上 |
| **AT&S** | ATS AT | 奧地利 | 部分 | ~8% | #5 | 同上 |

**Morgan Stanley 觀點（2026-02）：** 升評欣興 + 南電，看好 AI-led ABF 載板 up-cycle，2025-2030 ABF 市場 CAGR 16.1%（vs 過去 9%）  
**單機含量：** ABF Substrate $20.3K（+82% vs GB300）  
**下修風險：** 日系 Ibiden 對 NVDA 直供仍有競爭壓力。

---

## 9 · 被動元件（MLCC / 電感）

| 公司 | 代號 | 角色 | VR200 入列 | 估計份額 | 排名 | 來源 |
|---|---|---|---|---|---|---|
| **國巨** | 2327 | MLCC（高容、車規） | ✅ 🟢H | 全球 #3 MLCC（~13%）🟢H | #3 全球 | 業界 |
| **村田** | 6981 JP | MLCC #1 | ✅ | ~31% | **#1** | — |
| **TDK** | 6762 JP | MLCC | ✅ | ~10% | — | — |
| **奇力新** | 2456 | 電感 | 🟡 | ❓ | — | — |

**單機含量：** MLCC $4.3K（+182%）  
**下修風險：** MLCC 被動元件單價低，雖漲幅大但金額占比仍 <1% BOM。

---

## 10 · ODM / 整櫃組裝（L10）

> NVIDIA 改交付 L10（運算硬體預裝）整套伺服器，ODM 角色升級為「整櫃 SI」

| 公司 | 代號 | 角色 | VR200 入列 | 估計份額 | 排名 | 來源 |
|---|---|---|---|---|---|---|
| **鴻海/工業富聯** | 2317 / 601138 | 最大 L10 整櫃組裝商 | ✅ 🟢H | **~45-50%** 🟡M | **#1** | 業界共識 |
| **廣達** | 2382 | 整櫃 + 主機板（QCT） | ✅ 🟢H | ~25-30% 🟡M | #2 | 同上 |
| **緯穎** | 6669 | hyperscaler 客製化 | ✅ 🟢H | ~10-15% 🟠L | #3 | 同上 |
| **緯創** | 3231 | GB300/VR200 整櫃 | ✅ 🟢H | ~5-10% 🟠L | #4 | 同上 |
| **英業達** | 2356 | 部分 | 🟡 | ❓ | — | 業界 |

**單機含量：** Rack assembly value add $28.8K（+29%）  
**下修風險：** Nvidia 整合度提高（直接賣 L10），ODM 利潤率可能被壓縮。

---

## 11 · 連接器 / 銅纜 / 光通訊

| 公司 | 代號 | 角色 | VR200 入列 | 估計份額 | 排名 | 來源 |
|---|---|---|---|---|---|---|
| **嘉澤** | 3533 | GPU socket、高速連接器 | ✅ 🟢H | ~35-40%（GB200 socket）🟡M | **#1 socket** | 業界 |
| **凡甲** | 3526 | 高速連接器 | ✅ 🟡M | ❓ | — | — |
| **正崴** | 2392 | 高速連接器 | 🟡 | ❓ | — | — |
| **信驊** | 5274 | BMC（伺服器管理晶片） | ✅ 🟢H | ~70% 全球 BMC 🟢H | **#1 BMC** | 業界 |
| **Astera Labs** | ALAB US | AEC Retimer | ✅ 🟢H | 主供 🟢H | **#1 AEC** | substack/同上 |
| **Marvell** | MRVL US | AEC DSP / 光通訊 DSP | ✅ 🟢H | 雙雄之一 | #2 | 同上 |
| **Credo** | CRDO US | AEC | ✅ 🟡M | 第三 | #3 | 同上 |

**機櫃內互連策略：**
- **VR200 仍以銅纜（AEC）為主**（rack 內 3-7m）
- **CPO（光通訊）2027+ 才大規模**（rack 間）
- 224G SerDes 全面導入，AEC 含量 +30~50%

---

## 12 · 投資地圖總結（不分國別 × 確定性）

### 🟢 最高確定性（VR200 必有單 + 法人共識多源）
| 標的 | 代號 | 主要含量 |
|---|---|---|
| **NVIDIA** | NVDA | GPU + CPU + 網通晶片設計 |
| **TSMC** | 2330/TSM | N3P 代工 + CoWoS |
| **SK Hynix** | 000660 KS | HBM4 70% |
| **台達電** | 2308 | HVDC 電源 |
| **奇鋐** | 3017 | 水冷板 #1 |
| **欣興** | 3037 | ABF + 高層 PCB |
| **鴻海** | 2317 | L10 整櫃 |
| **信驊** | 5274 | BMC #1 |

### 🟡 新故事 / 入列 VR200 ⭐
| 標的 | 代號 | 看點 |
|---|---|---|
| **臻鼎-KY** | 4958 | PCB 首度入列 |
| **定穎投控** | 3715 | PCB 首度入列 |
| **南亞科** | 2408 | LPDDR5X 切入 NVDA |
| **富世達** | 6805 | QDC 首席 |
| **雙鴻** | 3324 | AWS Trainium + 水冷 |
| **Astera Labs** | ALAB | AEC Retimer 寡頭 |

### 🟠 間接受惠 / 競爭分散
| 標的 | 代號 | 備註 |
|---|---|---|
| **健策** | 3653 | 均熱片 +3x；MCL 路線 Rubin Ultra 才放量 |
| **南電** | 8046 | ABF #2，欣興競爭 |
| **國巨** | 2327 | MLCC 金額占比小 |
| **金像電/健鼎** | 2368/3044 | PCB 中段 |
| **廣達/緯穎/緯創** | 2382/6669/3231 | ODM 利潤可能被 NVDA 壓 |

### 🔴 觀察 / 風險端
| 標的 | 代號 | 為何 |
|---|---|---|
| **Micron** | MU | 沒進 VR200 HBM4 主供 |
| **Intel/AMD** | INTC/AMD | Vera Arm CPU 取代 x86 |
| **Marvell** | MRVL | AEC vs CPO 過渡期，AEC 不退也不爆 |

---

## 13 · 關鍵風險時序

| 風險 | 時點 | 影響 |
|---|---|---|
| HBM4 22 TB/s spec miss → 已下修 | 已發生（2026 Q1） | Rubin 出貨 29% → 22% |
| Rubin Ultra 從 4-die → 2-die | 2027 量產前 | 載板/PCB/散熱單機含量可能 -10~20% |
| CPO 大規模導入 | 2027+ | 銅纜 AEC 廠（ALAB/CRDO/MRVL）天花板 |
| MCL（健策）vs MCCP（奇鋐）路線 | Rubin Ultra 決定 | 健策若被選中是大利多 |
| L10 整合 → ODM 議價力下降 | 2026~ | 鴻海/廣達毛利壓縮 |
| 台海地緣 | 持續 | 大馬/越南/泰國產能轉移加速 |

---

## Sources

| # | URL | 摘要 |
|---|---|---|
| 1 | https://wccftech.com/nvidia-vera-rubin-rack-hit-with-memory-price-surge-pushing-hbm4-lpddr5x-bill-to-2m-of-7-8m-total | Morgan Stanley VR200 BOM 拆解 $7.8M |
| 2 | https://www.techpowerup.com/forums/threads/nvidia-lowers-hbm4-specs-for-vera-rubin-vr200-as-memory-suppliers-miss-22-tb-s-target.346983 | HBM4 spec miss、SK Hynix 70% / Samsung 30% |
| 3 | https://letsdatascience.com/news/nvidia-secures-hbm4-suppliers-for-vera-rubin-154cf0e7 | HBM4 供應比例（Micron 未入列） |
| 4 | https://www.sdxcentral.com/news/nvidias-rubin-gpus-hit-the-brakes-as-hbm4-memory-drought-threatens-jensens-supply-chain-magic-report | Rubin 出貨 29% → 22% |
| 5 | https://ieknet.iek.org.tw/ieknews/news_more.aspx?actiontype=ieknews&indu_idno=0&nsl_id=31bc295574de46158185a5d877ca68ee | IEK：奇鋐/雙鴻/富世達/台達/欣興/定穎/臻鼎 入列 |
| 6 | https://tw.stock.yahoo.com/news/%E8%BC%9D%E9%81%94rubin%E5%8D%87%E7%B4%9A-%E5%B8%B6%E6%97%BA%E4%BE%9B%E6%87%89%E9%8F%88-201000789.html | 同上 IEK 內容轉載 |
| 7 | https://wantrich.chinatimes.com/news/20251104900101-420101 | 大摩：散熱 GB300 +20%, VR200 +17% |
| 8 | https://www.ctee.com.tw/search/%E9%9B%99%E9%B4%BB%E3%80%81%E5%A5%87%E9%8B%90 | 工商時報散熱大全 |
| 9 | https://samuel6788.substack.com/p/rubin-147 | AEC vs 光通訊：VR200 仍以 AEC 為主 |
| 10 | https://www.investing.com/news/stock-market-news/morgan-stanley-upgrades-unimicron-nypcb-on-ailed-abf-substrate-upcycle-4519224 | 大摩升評欣興/南電 |
| 11 | https://fspinvest.co.za/morgan-stanley-just-flagged-the-real-bottleneck-in-the-ai-chip-race | ABF 五大廠占 74%（欣興/南電/Ibiden/Shinko/AT&S） |
| 12 | https://www.mordorintelligence.com/industry-reports/advanced-ic-substrates-market | ABF 前五大占 60%、無單一超 18% |
| 13 | https://www.nvidia.com/en-us/data-center/vera-rubin-nvl72 | NVDA 官方 VR NVL72 規格 |
| 14 | https://www.facebook.com/pocketstock/posts/940037422208993 | 高盛雙鴻 EPS：56.2 / 71.65 |
| 15 | https://www.storagereview.com/zh-TW/news/nvidia-launches-vera-rubin-architecture-at-ces-2026-the-vr-nvl72-rack | NVLink-C2C 1.8TB/s 規格 |
| 16 | https://wealth.businessweekly.com.tw/GArticle.aspx?id=ARTL003017561 | 商周：台達電/健策/鴻海 VR200 機會 |

---

**報告完成 2026-05-21 11:30 UTC** · 主要資料更新至 2026 年 5 月 · 技術細節以 NVIDIA 官方 + Morgan Stanley 研報為基準
