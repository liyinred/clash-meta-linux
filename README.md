# 自用clash规则,cn域名和特定网站直连(黑名单模式)
**目前 Clash 支持的规则类型如下：**

- DOMAIN-SUFFIX：域名后缀匹配
- DOMAIN：域名匹配
- DOMAIN-KEYWORD：域名关键字匹配
- IP-CIDR：IP 段匹配
- SRC-IP-CIDR：源 IP 段匹配
- GEOIP：GEOIP 数据库（国家代码）匹配
- DST-PORT：目标端口匹配
- SRC-PORT：源端口匹配
- PROCESS-NAME：源进程名匹配
- RULE-SET：Rule Provider 规则匹配
- MATCH：全匹配

```yaml
- DOMAIN-KEYWORD,dwai,🎯 全球直连
- DOMAIN-KEYWORD,cn,🎯 全球直连
```
