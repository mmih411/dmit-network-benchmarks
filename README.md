# DMIT 测速完全手册：三大机房延迟/丢包/路由实测数据，香港/洛杉矶/东京哪个最适合你？（附全套餐价格表与当前折扣码）

上个月帮一个做跨境独立站的朋友选 VPS，折腾了一周。他的访客七成来自国内，偏偏之前用的美西机器晚高峰延迟飙到 350ms，页面加载肉眼可见地卡。我建议他试试 DMIT，结果他在洛杉矶 Premium 上跑了三天，一句话反馈："感觉像换了一台机器。"

DMIT 测速是选这家 VPS 之前最该做的功课。测速数据直接决定你要选哪个机房、哪条线路，买错了退款虽然支持但也麻烦。这篇把各机房的测试 IP、延迟区间、路由特点、以及适用场景都写清楚，顺手把全套餐价格和当前折扣码附上，省得你还要再找一遍。

---

## DMIT 是什么：先搞清楚它的底层逻辑

**DMIT 是一家专注网络质量的 VPS 服务商**，2018 年开始运营，纽约注册公司，华人团队背景，主营洛杉矶、香港、东京三个机房的 KVM 虚拟化服务器。它跟那些转售堆配置的低价商家不一样——DMIT 是自持网络资源的上游服务商，直接持有 CN2 GIA、CMIN2、CMI 等精品线路带宽，甚至给部分小商家提供白牌服务。

这意味着什么？简单说：你的流量出口由它自己控制，不会因为上游服务商的网络抖动而无能为力。

三网优化这件事，DMIT 按机房分了三个系列：

- **Premium**：电信/联通/移动三网双向 CN2 GIA，最优路由，延迟最低，价格最贵
- **Eyeball**：电信联通走 AS9929，移动走 CMIN2，综合路由次一档，性价比更高
- **Tier 1**：国际线路，无中国大陆方向优化，适合面向全球用户或做全球分发

---

## DMIT 测速：各机房延迟数据与测试 IP

做 DMIT 测速最直接的方法是拿官方测试 IP 自己 ping，加上在目标节点跑 wget 下速度，比任何文章里的数字都准。各机房测试 IP 汇总如下：

| 机房 | 线路系列 | 测试 IPv4 | 测试 IPv6 |
|------|----------|-----------|-----------|
| 洛杉矶（LAX）Pro | CN2 GIA | 154.17.2.2 | — |
| 洛杉矶（LAX）EB | CMIN2 | 154.17.226.2 | 2605:52c0:1:3:2c2a:59ff:fe05:65c2 |
| 香港（HKG）Pro | CN2 GIA | 103.117.100.2 | — |
| 东京（TYO）Pro | CN2 GIA | — | 见 Looking Glass |

👉 [前往 DMIT 官网查看完整机房测速文件](https://www.dmit.io/aff.php?aff=13832)

**延迟参考区间（国内主流城市 ping）：**

洛杉矶 Premium 的物理距离最远，但 CN2 GIA 双向优化做了不少事——国内到 LAX Pro 延迟一般落在 150–180ms，三网一致性好，晚高峰也基本维持在这个水平。

香港机房物理距离近太多了。HKG Pro 对国内用户，延迟通常在 10–30ms，HKG Eyeball（CMI 优化）也能跑到 20–50ms。如果你的业务需要实时响应或者用户体验对速度非常敏感，香港节点优势明显。

东京比洛杉矶近，比香港远一点。TYO Pro 的国内延迟大概在 60–90ms 之间，适合需要日本 IP、或者面向日本用户的场景。

---

## 三大机房横向对比：选错机房比选错套餐更亏

说实话，很多人纠结套餐的时间比选机房长，这个优先级反了。

**洛杉矶（LAX）**是 DMIT 产品线最全的机房，套餐覆盖从年付 $36.9 的入门 T1 一直到 $88/月的旗舰 Premium，选择空间大。用原生 IP，Netflix、TikTok 等流媒体解锁率高，外贸、建站、科学上网都有对应产品。如果预算有限但又想要 CN2 GIA 效果，LAX Pro 的 MALIBU 年付方案是目前可以入手的最便宜选项。

**香港（HKG）**延迟最低，但价格比洛杉矶贵不少。HKG Pro 的入门 TINY 要 $39.90/月，同样配置在洛杉矶 Eyeball 系列要便宜一大截。香港节点特别适合：面向国内用户的低延迟服务、游戏服务器（延迟差 10ms 在某些场景下是真实体验差距）、以及对响应速度有严格要求的 API 服务。

**东京（TYO）**介于两者之间。延迟比洛杉矶好，价格比香港低，CN2 GIA 的 Pro 系列覆盖，也有 T1 国际线路方案年付 $36.9 起。特别适合面向东亚、东南亚市场的业务，以及需要日本 IP 的场景。注意：东京 Eyeball 系列已于近期下架，现在只有 Pro 和 T1 两档可选。

---

## 当前 DMIT 官方折扣码（季付及以上生效）

这部分直接列官方促销码，适用条件写清楚，对号入座：

| 优惠码 | 适用范围 | 折扣 |
|--------|----------|------|
| `LAX-EB-LAUNCH-NON-MONTHLY-RECURRING-20OFF` | 洛杉矶 Eyeball 系列，季付及以上 | 8折循环（每次续费都打折） |
| `202510_HKG_TYO_PRO_20OFF_RECURRING` | 香港/东京 Premium 系列，季付及以上 | 8折循环 |
| `202510_HKG_TYO_T1_30OFF_RECURRING` | 香港/东京 T1 系列（不含 WEE），季付及以上 | 7折循环 |
| `2025-TYO-T1-HI-GSL-MONTHLY-10OFF` | 东京 T1 TINY 及以上，月付 | 9折 |
| `2025-TYO-T1-HI-GSL-NON-MONTHLY-30OFF` | 东京 T1 TINY 及以上，季付及以上 | 7折循环 |
| `LAX-T1-ANNUALLY-RECUR-30-OFF` | 洛杉矶 T1 TINY 及以上，年付 | 7折循环 |
| `LAX-T1-WEE-ANNUALLY-RECUR-10-OFF` | 洛杉矶 T1 WEE，年付 | 9折 |
| `SJC-Unmetered-Annually-30OFF` | 圣何塞不限流量系列，年付 | 7折循环 |

使用方式：进购物车找 "Apply Promo Code" 输入框，粘贴优惠码，点 "Validate Code" 验证，确认折扣到账再结账。注意大小写，建议直接复制粘贴。

循环折扣这个政策挺良心的——续费不涨价，不存在"首年低价坑"。

👉 [选好套餐后前往 DMIT 官网结账](https://www.dmit.io/aff.php?aff=13832)

---

## DMIT 全套餐价格表（完整版）

价格以官网为准，下方数据基于近期官网页面，随时可能调整，购买前请在官网核验。

### 洛杉矶 Premium 系列（三网 CN2 GIA 双向优化）

**AN4 平台（LAX.AN4.Pro）**

| 套餐 | CPU | 内存 | 硬盘 | 流量/带宽 | 价格 | 购买 |
|------|-----|------|------|-----------|------|------|
| TINY | 1核 | 2GB | 20GB SSD | 1000GB / 1Gbps | $88.88/年 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=237) |
| Pocket | 2核 | 2GB | 40GB SSD | 1500GB / 4Gbps | $159.98/年 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=238) |
| STARTER | 2核 | 2GB | 80GB SSD | 3000GB / 10Gbps | $29.90/月 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=239) |
| MINI | 4核 | 4GB | 80GB SSD | 5000GB / 10Gbps | $58.88/月 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=240) |
| MICRO | 4核 | 4GB | 160GB SSD | 7000GB / 10Gbps | $74.99/月 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=241) |
| MEDIUM | 6核 | 8GB | 160GB SSD | 15000GB / 10Gbps | $168.88/月 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=242) |
| LARGE | 8核 | 16GB | 320GB SSD | 25000GB / 10Gbps | $338.88/月 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=243) |
| GIANT | 12核 | 24GB | 640GB SSD | 50000GB / 10Gbps | $619.99/月 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=244) |

**AN5 平台（LAX.AN5.Pro，搭载最新 AMD EPYC 9005 系列）**

| 套餐 | CPU | 内存 | 硬盘 | 流量/带宽 | 价格 | 购买 |
|------|-----|------|------|-----------|------|------|
| TINY | 1核 | 2GB | 20GB SSD | 1000GB / 1Gbps | $119.99/年 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=100) |
| Pocket | 2核 | 2GB | 40GB SSD | 1500GB / 4Gbps | $203.90/年 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=137) |
| STARTER | 2核 | 2GB | 80GB SSD | 3000GB / 10Gbps | $38.90/月 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=56) |
| MINI | 4核 | 4GB | 80GB SSD | 5000GB / 10Gbps | $76.90/月 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=58) |
| MICRO | 4核 | 4GB | 160GB SSD | 7000GB / 10Gbps | $99.90/月 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=81) |
| MEDIUM | 6核 | 8GB | 160GB SSD | 15000GB / 10Gbps | $219.90/月 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=82) |
| LARGE | 8核 | 16GB | 320GB SSD | 25000GB / 10Gbps | $2759.40/半年 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=61) |
| GIANT | 12核 | 24GB | 640GB SSD | 50000GB / 10Gbps | $839.90/月 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=98) |

### 洛杉矶 Eyeball 系列（电信联通 AS9929，移动 CMIN2 回程）

**AN4 平台（LAX.AN4.EB）**

| 套餐 | CPU | 内存 | 硬盘 | 流量/带宽 | 价格 | 购买 |
|------|-----|------|------|-----------|------|------|
| TINY | 1核 | 2GB | 20GB SSD | 1500GB / 2Gbps | $88.88/年 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=245) |
| Pocket | 2核 | 2GB | 40GB SSD | 3000GB / 4Gbps | $159.98/年 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=246) |
| STARTER | 2核 | 2GB | 80GB SSD | 5000GB / 10Gbps | $29.90/月 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=247) |
| MINI | 4核 | 4GB | 80GB SSD | 10000GB / 10Gbps | $58.88/月 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=248) |
| MICRO | 4核 | 4GB | 160GB SSD | 14000GB / 10Gbps | $74.99/月 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=249) |
| MEDIUM | 6核 | 8GB | 160GB SSD | 30000GB / 10Gbps | $168.88/月 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=250) |
| LARGE | 8核 | 16GB | 320GB SSD | 50000GB / 10Gbps | $338.88/月 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=251) |
| GIANT | 12核 | 24GB | 640GB SSD | 100000GB / 10Gbps | $619.99/月 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=252) |

**AN5 平台（LAX.AN5.EB）**

| 套餐 | CPU | 内存 | 硬盘 | 流量/带宽 | 价格 | 购买 |
|------|-----|------|------|-----------|------|------|
| TINY | 1核 | 2GB | 20GB SSD | 1500GB / 2Gbps | $119.99/年 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=189) |
| Pocket | 2核 | 2GB | 40GB SSD | 3000GB / 4Gbps | $203.90/年 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=190) |
| STARTER | 2核 | 2GB | 80GB SSD | 5000GB / 10Gbps | $38.90/月 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=191) |
| MINI | 4核 | 4GB | 80GB SSD | 10000GB / 10Gbps | $76.90/月 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=192) |
| MICRO | 4核 | 4GB | 160GB SSD | 14000GB / 10Gbps | $99.90/月 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=193) |
| MEDIUM | 6核 | 8GB | 160GB SSD | 30000GB / 10Gbps | $219.90/月 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=194) |
| LARGE | 8核 | 16GB | 320GB SSD | 50000GB / 10Gbps | $2759.40/半年 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=195) |
| GIANT | 12核 | 24GB | 640GB SSD | 100000GB / 10Gbps | $839.90/月 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=196) |

### 洛杉矶 T1 系列（国际线路，无中国优化）

**VOLUME 系列（AN5，大流量型）**

| 套餐 | CPU | 内存 | 硬盘 | 流量/带宽 | 价格 | 购买 |
|------|-----|------|------|-----------|------|------|
| V2C2G | 2核 | 2GB | 40GB SSD | 5000GB / 10Gbps | $14.90/月 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=169) |
| V2C4G | 2核 | 4GB | 80GB SSD | 10000GB / 10Gbps | $23.90/月 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=170) |
| V4C4G | 4核 | 4GB | 120GB SSD | 20000GB / 10Gbps | $36.90/月 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=171) |
| V4C8G | 4核 | 8GB | 160GB SSD | 40000GB / 10Gbps | $52.90/月 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=180) |
| V8C16G | 8核 | 16GB | 240GB SSD | 80000GB / 10Gbps | $119.90/月 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=172) |
| V12C24G | 12核 | 24GB | 320GB SSD | 160000GB / 10Gbps | $199.90/月 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=173) |

**GENERAL 系列（AN4）**

| 套餐 | CPU | 内存 | 硬盘 | 流量/带宽 | 价格 | 购买 |
|------|-----|------|------|-----------|------|------|
| G2C4G | 2核 | 4GB | 80GB SSD | 4000GB / 10Gbps | $16.90/月 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=234) |
| G4C8G | 4核 | 8GB | 160GB SSD | 8000GB / 10Gbps | $36.90/月 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=235) |
| G8C16G | 8核 | 16GB | 320GB SSD | 12000GB / 10Gbps | $79.90/月 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=236) |
| G12C24G | 12核 | 24GB | 480GB SSD | 240000GB / 10Gbps | $119.90/月 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=174) |
| G16C32G | 16核 | 32GB | 640GB SSD | 320000GB / 10Gbps | $199.90/月 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=175) |

**入门小套餐（年付 / 月付）**

| 套餐 | CPU | 内存 | 硬盘 | 流量 | 价格 | 购买 |
|------|-----|------|------|------|------|------|
| WEE | 1核 | 1GB | 20GB SSD | 1000GB | $36.90/年 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=71) |
| TINY | 1核 | 1GB | 20GB SSD | 2000GB | $6.90/月 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=116) |
| STARTER | 2核 | 2GB | 40GB SSD | 4000GB | $12.90/月 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=117) |
| MINI | 2核 | 4GB | 80GB SSD | 8000GB | $21.90/月 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=118) |
| MICRO | 4核 | 4GB | 120GB SSD | 16000GB | $32.90/月 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=119) |

### 香港 Premium 系列（三网 CN2 GIA，延迟 10–30ms）

| 套餐 | CPU | 内存 | 硬盘 | 流量/带宽 | 价格 | 购买 |
|------|-----|------|------|-----------|------|------|
| TINY | 1核 | 1GB | 20GB SSD | 500GB / 1Gbps | $39.90/月 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=123) |
| STARTER | 1核 | 2GB | 40GB SSD | 1000GB / 1Gbps | $79.90/月 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=124) |
| MINI | 2核 | 2GB | 60GB SSD | 1500GB / 1Gbps | $119.90/月 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=125) |
| MICRO | 4核 | 4GB | 80GB SSD | 2000GB / 1Gbps | $159.90/月 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=126) |
| MEDIUM | 4核 | 8GB | 160GB SSD | 2500GB / 1Gbps | $179.90/月 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=127) |
| LARGE | 8核 | 16GB | 320GB SSD | 3000GB / 1Gbps | $239.90/月 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=128) |
| GIANT | 8核 | 24GB | 640GB SSD | 6000GB / 1Gbps | $499.90/月 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=129) |

### 香港 Eyeball 系列（三网 CMI 优化）

| 套餐 | CPU | 内存 | 硬盘 | 流量/带宽 | 价格 | 购买 |
|------|-----|------|------|-----------|------|------|
| TINYv2 | 1核 | 1GB | 20GB SSD | 1000GB / 1Gbps | $29.90/月 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=210) |
| STARTERv2 | 1核 | 2GB | 40GB SSD | 2000GB / 2Gbps | $59.90/月 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=211) |
| MINIv2 | 2核 | 2GB | 60GB SSD | 3000GB / 2Gbps | $89.90/月 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=212) |
| MICROv2 | 4核 | 4GB | 80GB SSD | 4000GB / 4Gbps | $129.90/月 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=213) |
| MEDIUMv2 | 4核 | 8GB | 160GB SSD | 6000GB / 4Gbps | $199.90/月 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=214) |
| LARGEv2 | 8核 | 16GB | 320GB SSD | 12000GB / 4Gbps | $389.90/月 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=215) |
| GIANTv2 | 8核 | 24GB | 640GB SSD | 24000GB / 4Gbps | $789.90/月 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=216) |

### 香港 T1 系列（国际线路）

| 套餐 | CPU | 内存 | 硬盘 | 流量 | 价格 | 购买 |
|------|-----|------|------|------|------|------|
| WEE | 1核 | 1GB | 20GB SSD | 1000GB | $36.90/年 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=197) |
| TINY | 1核 | 1GB | 20GB SSD | 2000GB | $6.90/月 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=198) |
| STARTER | 1核 | 2GB | 40GB SSD | 4000GB | $12.90/月 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=199) |
| MINI | 2核 | 2GB | 60GB SSD | 8000GB | $21.90/月 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=200) |
| MICRO | 4核 | 4GB | 80GB SSD | 16000GB | $32.90/月 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=201) |
| MEDIUM | 4核 | 8GB | 160GB SSD | 32000GB | $49.90/月 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=202) |
| LARGE | 8核 | 16GB | 320GB SSD | 64000GB | $99.90/月 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=203) |
| GIANT | 8核 | 24GB | 640GB SSD | 128000GB | $199.90/月 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=204) |

### 东京 Premium 系列（三网 CN2 GIA）

| 套餐 | CPU | 内存 | 硬盘 | 流量/带宽 | 价格 | 购买 |
|------|-----|------|------|-----------|------|------|
| TINY | 1核 | 1GB | 20GB SSD | 500GB / 1Gbps | $21.90/月 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=138) |
| STARTER | 1核 | 2GB | 40GB SSD | 1000GB / 1Gbps | $39.90/月 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=139) |
| MINI | 2核 | 2GB | 60GB SSD | 2000GB / 1Gbps | $79.90/月 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=140) |
| MICRO | 4核 | 4GB | 80GB SSD | 4000GB / 1Gbps | $159.90/月 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=141) |
| MEDIUM | 4核 | 8GB | 160GB SSD | 5000GB / 1Gbps | $259.90/月 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=142) |
| LARGE | 8核 | 16GB | 320GB SSD | 8000GB / 1Gbps | $429.90/月 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=143) |
| GIANT | 8核 | 24GB | 640GB SSD | 15000GB / 1Gbps | $799.90/月 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=144) |

### 东京 Eyeball 系列（三网 CMI 优化）

| 套餐 | CPU | 内存 | 硬盘 | 流量/带宽 | 价格 | 购买 |
|------|-----|------|------|-----------|------|------|
| TINY | 1核 | 1GB | 20GB SSD | 1000GB / 1Gbps | $25.90/月 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=221) |
| STARTER | 1核 | 2GB | 40GB SSD | 2000GB / 2Gbps | $55.90/月 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=222) |
| MINI | 2核 | 2GB | 60GB SSD | 3000GB / 2Gbps | $85.90/月 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=223) |
| MICRO | 4核 | 4GB | 80GB SSD | 4000GB / 4Gbps | $119.90/月 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=224) |
| MEDIUM | 4核 | 8GB | 160GB SSD | 6000GB / 4Gbps | $179.90/月 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=225) |
| LARGE | 8核 | 16GB | 320GB SSD | 12000GB / 4Gbps | $369.90/月 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=226) |
| GIANT | 8核 | 24GB | 640GB SSD | 24000GB / 4Gbps | $749.90/月 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=227) |

### 东京 T1 系列（国际线路）

| 套餐 | CPU | 内存 | 硬盘 | 流量 | 价格 | 购买 |
|------|-----|------|------|------|------|------|
| WEE | 1核 | 1GB | 20GB SSD | 1000GB | $36.90/年 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=228) |
| TINY | 1核 | 1GB | 20GB SSD | 2000GB | $6.90/月 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=131) |
| STARTER | 1核 | 2GB | 40GB SSD | 4000GB | $12.90/月 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=132) |
| MINI | 2核 | 2GB | 60GB SSD | 8000GB | $21.90/月 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=133) |
| MICRO | 4核 | 4GB | 80GB SSD | 16000GB | $32.90/月 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=134) |
| MEDIUM | 4核 | 8GB | 160GB SSD | 32000GB | $49.90/月 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=135) |
| LARGE | 8核 | 16GB | 320GB SSD | 64000GB | $99.90/月 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=136) |
| GIANT | 8核 | 24GB | 640GB SSD | 128000GB | $199.90/月 | [ 选择此方案](https://www.dmit.io/aff.php?aff=13832&pid=229) |

---

## 超量了怎么办：流量用完不会直接关机

这点挺重要，不少人买 VPS 前会担心流量超额直接停服。

DMIT 的处理方式是限速而不是断连：超出月流量后，带宽会自动降到 50–100Mbps（T1 系列），等到下个月流量重置后自动恢复正常速率。Pro/EB 系列部分套餐支持类似机制。大流量业务选 T1 系列特别省心，不用担心跑着跑着突然没网。

IP 被墙的话，Premium 和 Eyeball 系列 IP 每 15 天可以免费换一次，条件是 IP 确实被大陆封锁。其他情况换 IP 收费 $5/次，有明确政策，不是那种联系客服看心情的处理方式。

---

## 退款和付款：买错了能退吗

退款政策：购买 3 天内且使用流量不超过 30GB，支持全额退款（扣支付网关手续费）。超过 3 天但在 30 天内，按剩余时间和剩余金额孰低退款。

所以想试一试线路质量的，入手最便宜的 WEE 年付（$36.90），3 天内 ping 一下、跑个测速，不满意退款，试错成本基本是零。我自己当时就是这么摸底的。

付款支持：支付宝、微信、PayPal、信用卡，对国内用户来说支付完全没障碍。

---

## 根据场景快速选机房和线路

问题来了：数据看完，我还是不知道买哪个。

以下是直接结论：

**电信用户、主要面向国内访客、对速度要求高** → 洛杉矶 LAX Pro 或香港 HKG Pro，三网 CN2 GIA 双向优化，延迟和稳定性都是最优档

**联通 / 移动用户、预算有限** → 洛杉矶 LAX Eyeball，CMIN2 回程对这两个运营商体验好，价格比 Pro 低一截，配合 `LAX-EB-LAUNCH-NON-MONTHLY-RECURRING-20OFF` 季付享 8 折

**主要面向全球用户、不需要中国优化、流量大** → 洛杉矶 T1 VOLUME 系列，$14.90/月起，大流量方案性价比高

**面向日本 / 东亚用户，或需要日本 IP** → 东京 TYO Pro，CN2 GIA，延迟好，价格比香港低

**预算极有限、先试试水** → 香港 / 东京 / 洛杉矶 T1 WEE，年付 $36.90，三家都能试，国际线路无中国优化，但至少能验证机房稳定性

👉 [对比所有套餐，找到最适合你的方案](https://www.dmit.io/aff.php?aff=13832)

---

## FAQ：做 DMIT 测速前后最常见的几个问题

**Q：DMIT 测速用哪个 IP 比较准？**

A：洛杉矶 Pro 系列用 154.17.2.2，Eyeball 系列用 154.17.226.2，香港 Pro 用 103.117.100.2。直接 ping 这几个 IP，不同时段多测几次，晚高峰（21:00–23:00）那段最能体现真实延迟。

**Q：Eyeball 和 Premium 差多少，值不值得多花钱升？**

A：路由差异在于去程。Premium 是电信 / 联通 / 移动三网双向 CN2 GIA；Eyeball 去程走 AS9929，移动走 CMIN2，回程 CMIN2。实测差距在延迟 10–20ms 左右，晚高峰稳定性 Premium 略好。如果是跑静态网站或者非实时应用，Eyeball 够用。游戏或者低延迟敏感的业务，Premium 更稳。

**Q：T1 系列是不是就没用了？**

A：不是。T1 适合的场景：面向全球用户（国际线路质量好）、大流量需求（价格便宜流量多）、或者纯粹需要一个稳定境外 IP 跑服务的场景。国内访问速度不是 T1 的强项，但这本来也不是它的定位。

**Q：香港机房经常缺货是真的吗？**

A：是的，热门套餐确实经常售罄，尤其是 HKG Pro 系列。补货时间不定期。如果看到有货且符合需求，不用太犹豫。

**Q：优惠码和月付方案能叠用吗？**

A：大部分循环折扣码只对季付及以上生效，月付通常不享受折扣。东京 T1 有月付 9 折码（`2025-TYO-T1-HI-GSL-MONTHLY-10OFF`）是少数例外。如果打算长期用，季付或年付的综合算下来比月付划算明显。

**Q：IP 被封怎么办？**

A：Premium 和 Eyeball 系列，IP 被大陆封锁时可以每 15 天免费申请更换一次。主动申请换 IP（非封锁原因）收费 $5/次。

---

所有套餐在官网实时有货情况和最新价格以 DMIT 官方页面为准，热门套餐随时售罄，价格也可能调整。

👉 [立即前往 DMIT 查看最新套餐与折扣](https://www.dmit.io/aff.php?aff=13832)
