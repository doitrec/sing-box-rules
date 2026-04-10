# sing-box-rules

Auto-built sing-box binary rule sets (`.srs`) from [SukkaW/Surge](https://github.com/SukkaW/Surge) source JSON.

每天自动从 [ruleset.skk.moe](https://ruleset.skk.moe) 下载 source JSON，编译为 `.srs` binary 格式，发布到 GitHub Releases。

## 使用方式

在 sing-box 配置的 `rule_set` 中使用：

```json
{
  "tag": "sukka-reject-domainset",
  "type": "remote",
  "format": "binary",
  "url": "https://github.com/doitrec/sing-box-rules/releases/latest/download/reject.srs",
  "download_detour": "proxy-main",
  "update_interval": "1d"
}
```

## 包含的规则集

| 文件 | 来源 | 说明 |
|------|------|------|
| `reject.srs` | domainset/reject | 广告/隐私/恶意域名（~12万条） |
| `reject_extra.srs` | domainset/reject_extra | 额外拦截域名（~9万条） |
| `reject_non_ip.srs` | non_ip/reject | 非 IP 拦截规则 |
| `reject_ip.srs` | ip/reject | IP 拦截规则 |
| `domestic.srs` | non_ip/domestic | 国内域名 |
| `direct.srs` | non_ip/direct | 直连域名 |
| `global.srs` | non_ip/global | 海外域名 |
| `china_ip.srs` | ip/china_ip | 中国 IP 段 |

## 致谢

- [SukkaW/Surge](https://github.com/SukkaW/Surge) - 规则数据来源
- [SagerNet/sing-box](https://github.com/SagerNet/sing-box) - `rule-set compile` 工具

