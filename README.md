# Cloudflare IP 地址段白名单

本仓库存储了 Cloudflare 官方发布的公开 IP 地址段，主要用于配合 **[IP测评 · 云享版]** 工具生成可用的代理/转发节点列表。

---

## 📦 文件说明

| 文件名 | 内容 | 用途 |
|--------|------|------|
| `ips-v4.txt` | Cloudflare IPv4 地址段（/24 网段） | 供测评工具随机组合 IP + 端口，生成可用节点 |
| `ips-v6.txt` | Cloudflare IPv6 地址段（/48 网段） | 供测评工具随机组合 IP + 端口，生成可用节点 |

---

## 🔗 数据来源

两个文件均来自 Cloudflare 官方公开 IP 列表：

- **IPv4**：https://www.cloudflare.com/ips-v4
- **IPv6**：https://www.cloudflare.com/ips-v6

> ⚠️ **注意**：Cloudflare 会不定期更新 IP 地址段，建议定期检查并更新本仓库的文件内容，以保证生成的节点地址仍然有效。

---

## 🛠️ 配合工具使用

本仓库的 IP 数据专为 **[IP测评 · 云享版]** 页面工具设计。该工具的工作流程如下：

1. 读取本仓库的 `ips-v4.txt` 和 `ips-v6.txt` 中的 IP 网段
2. 从网段中随机生成具体 IP 地址
3. 与用户指定的端口（如 `443`、`8443`、`2053` 等）组合成 `IP:端口` 格式
4. 进行连通性和延迟测评
5. 最终生成可用的 VLESS 节点链接

### 工具内置的默认端口列表

| 端口 | 说明 |
|------|------|
| `443` | HTTPS 标准端口 |
| `8443` | 备用 HTTPS 端口 |
| `2053` | Cloudflare 常用端口 |
| `2083` | Cloudflare 常用端口 |
| `2087` | Cloudflare 常用端口 |
| `2096` | Cloudflare 常用端口 |

> 💡 用户也可以在工具中自定义添加更多端口进行测试。

---

## 📥 获取文件的 Raw 链接

本仓库文件可通过以下 Raw 链接直接下载或引用：

```bash
# IPv4 地址列表
https://raw.githubusercontent.com/wt20230521/wtw20230521/main/ips-v4.txt

# IPv6 地址列表
https://raw.githubusercontent.com/wt20230521/wtw20230521/main/ips-v6.txt
```

---

## 📝 更新记录

| 日期 | 更新内容 |
|------|----------|
| 2026-07-09 | 首次上传，从 Cloudflare 官方源获取最新 IP 地址段 |

---
## 📡 实时优选IP数据源

以下链接由第三方项目维护，每小时自动更新：

| 类型 | 链接 |
|------|------|
| 高速优选IP（主用） | https://ips.gaoji.uk/best_ips.txt |
| 高速优选IP（备用） | https://raw.githubusercontent.com/svip-s/cloudflare_ip/refs/heads/main/best_ips.txt |

> 本仓库的 `ips-v4.txt` 和 `ips-v6.txt` 为官方原始CIDR网段，供备用或自定义测评使用。
## ⚠️ 注意事项

1. 本仓库仅存储静态 IP 数据，实际使用时请以官方最新数据为准。
2. IP 地址段会随时间变化，建议设置定期更新提醒（如每季度检查一次）。
3. 本数据仅供学习研究及合法合规用途使用。

---

<p align="right">最后更新时间：2026年7月9日</p>
