# TommyC1 Shadowrocket Rules

[![GitHub Pages](https://img.shields.io/badge/订阅链接-GitHub%20Pages-blue)](https://tommyc1.github.io/Shadowrocket-Rules/TommyC1.conf)

个人定制的 Shadowrocket 分流规则，基于 [johnshall/Shadowrocket-ADBlock-Rules-Forever](https://github.com/johnshall/Shadowrocket-ADBlock-Rules-Forever) 和 [LingJingMaster/Shadowrocket-Rules](https://github.com/LingJingMaster/Shadowrocket-Rules) 整合优化。

## ✨ 特性

| 功能 | 说明 |
|---|---|
| 🌐 分流规则 | 国内直连 + 国外代理，智能分流 |
| 🤖 AI 服务 | ChatGPT、Claude、Gemini 等走美国节点 |
| 💰 投资平台 | Robinhood、Charles Schwab 等走美国节点 |
| 🎬 流媒体 | Netflix、Disney+、Spotify 等走美国节点 |
| 📺 YouTube | 独立分组，自由选择节点 |
| 🔍 Google | 独立分组，自由选择节点 |
| 💻 开发工具 | GitHub、Stack Overflow 等 |
| 🛡️ 轻量去广告 | 屏蔽主要广告和隐私追踪 |
| 🔒 DNS 防污染 | DoH 加密 DNS + 国内域名指定国内 DNS |
| 🕵️ 防隐私追踪 | 拦截常见追踪器和分析 SDK |

## 📱 快速使用

### 方法一：订阅链接（推荐）

复制以下链接，在 Shadowrocket 中 **添加配置** → **粘贴链接**：

```
https://tommyc1.github.io/Shadowrocket-Rules/TommyC1.conf
```

### 方法二：扫码导入

> 在 Shadowrocket 中扫描下方二维码即可自动导入配置

### 方法三：手动下载

1. 下载 [TommyC1.conf](./TommyC1.conf)
2. 通过 AirDrop 或其他方式传到手机
3. 用 Shadowrocket 打开

## 🏗️ 代理组结构

```
✈️ 节点选择（主选择器）
├── ♻️ 自动选择（延迟最低）
├── 🇺🇸 美国节点
├── 🇭🇰 香港节点
├── 🇯🇵 日本节点
├── 🇸🇬 新加坡节点
├── 🇹🇼 台湾节点
└── DIRECT

🤖 AI服务 ──→ 默认: 🇺🇸 美国节点
💰 投资平台 ──→ 默认: 🇺🇸 美国节点
🎬 流媒体 ──→ 默认: 🇺🇸 美国节点
📺 YouTube ──→ 默认: ✈️ 节点选择
🔍 Google ──→ 默认: ✈️ 节点选择
💻 开发工具 ──→ 默认: ✈️ 节点选择
📱 Telegram ──→ 默认: ✈️ 节点选择
🍎 Apple ──→ 默认: DIRECT
🛡️ 广告拦截 ──→ 默认: REJECT
🐟 漏网之鱼 ──→ 默认: ✈️ 节点选择（代理优先）
```

## 🔧 规则匹配优先级

1. **HTTPDNS 拦截** — 防止 DNS 泄露
2. **轻量去广告** — 拦截主要广告域名和隐私追踪
3. **AI 服务** → 🇺🇸 美国节点
4. **投资平台** → 🇺🇸 美国节点
5. **流媒体** → 🇺🇸 美国节点
6. **YouTube** → 自选节点
7. **Google 服务** → 自选节点
8. **开发工具** → 自选节点
9. **Telegram** → 自选节点
10. **Apple 服务** → 默认直连
11. **其他国外服务** → 节点选择
12. **国内服务** → 直连
13. **GeoIP 中国** → 直连
14. **漏网之鱼** → 代理（安全优先）

## ⚙️ 自定义修改

### 添加需要走代理的域名

在 `[Rule]` 部分的合适位置添加：

```ini
DOMAIN-SUFFIX,example.com,✈️ 节点选择
```

### 添加需要走美国节点的域名

```ini
DOMAIN-SUFFIX,example.com,🇺🇸 美国节点
```

### 添加需要直连的域名

```ini
DOMAIN-SUFFIX,example.com,DIRECT
```

### 启用 HTTPS 去广告

1. 在配置中将 `[MITM]` 部分的 `enable = false` 改为 `enable = true`
2. 在 Shadowrocket 中：设置 → HTTPS 解密 → 生成新的 CA 证书 → 安装 → 信任

## 🔗 致谢

- [johnshall/Shadowrocket-ADBlock-Rules-Forever](https://github.com/johnshall/Shadowrocket-ADBlock-Rules-Forever) — 去广告规则参考
- [LingJingMaster/Shadowrocket-Rules](https://github.com/LingJingMaster/Shadowrocket-Rules) — 分流规则和代理组架构参考

## 📄 License

MIT License
