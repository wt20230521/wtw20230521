# Cloudflare IP 地址段白名单

本仓库存储了 Cloudflare 官方发布的公开 IP 地址段，主要用于配合 **IP测评 · 云享版** 工具生成候选 IP 列表，进行网络连通性和延迟测评。

---

## 📦 文件说明

| 文件名 | 内容 | 用途 |
|--------|------|------|
| `ips-v4.txt` | Cloudflare IPv4 地址段（CIDR 格式） | 供测评工具从网段中生成候选 IP |
| `ips-v6.txt` | Cloudflare IPv6 地址段（CIDR 格式） | 供测评工具从网段中生成候选 IP |

> ⚠️ **注意**：Cloudflare 官方公布的网段包含多种 CIDR 前缀（如 `/22`、`/20`、`/32`、`/48` 等），并非固定长度。

---

## 🔗 数据来源

两个文件均来自 Cloudflare 官方公开 IP 列表：

- **IPv4**：https://www.cloudflare.com/ips-v4
- **IPv6**：https://www.cloudflare.com/ips-v6
- **官方文档**：https://developers.cloudflare.com/fundamentals/concepts/cloudflare-ip-addresses/

> ⚠️ **注意**：Cloudflare 会不定期更新 IP 地址段，建议定期检查并更新本仓库的文件内容，以保证测评数据的准确性。

---

## 🛠️ 配合工具使用

本仓库的 IP 数据专为 **IP测评 · 云享版** 页面工具设计。该工具的工作流程如下：

1. 读取本仓库的 `ips-v4.txt` 和 `ips-v6.txt` 中的 IP 网段
2. 从网段中生成候选 IP 地址
3. 与用户指定的端口（如 `443`、`8443`、`2053`、`2083`、`2087`、`2096` 等）组合成 `IP:端口` 格式
4. 进行连通性和延迟测评
5. 筛选并输出低延迟的优质 IP

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

## 📡 第三方实时优选 IP（仅供参考）

以下链接由社区项目维护，更新频率较高，但筛选标准和准确性未经本仓库验证：

| 类型 | 链接 |
|------|------|
| 高速优选 IP（主用） | https://ips.gaoji.uk/best_ips.txt |
| 高速优选 IP（备用） | https://raw.githubusercontent.com/svip-s/cloudflare_ip/refs/heads/main/best_ips.txt |

> ⚠️ 这些数据源为社区贡献，本仓库不对其准确性和可用性负责。

---

## 📝 更新记录

| 日期 | 更新内容 | 数据来源校验 |
|------|----------|-------------|
| 2026-07-09 | 首次上传，同步 Cloudflare 官方最新 IP 段 | [ips-v4](https://www.cloudflare.com/ips-v4) / [ips-v6](https://www.cloudflare.com/ips-v6) |

### 更新计划
- 检查频率：建议每季度核对一次官方源
- 上次官方源校验时间：2026-07-09

---

## ⚠️ 注意事项

1. 本仓库仅存储静态 IP 数据，实际使用时请以官方最新数据为准。
2. IP 地址段会随时间变化，建议设置定期更新提醒（如每季度检查一次）。
3. 本数据仅供学习研究及网络测试用途，请遵守当地法律法规。

---

<p align="right">最后更新时间：2026年7月9日</p>
