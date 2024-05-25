<div align="center">
   <h1>自用clash规则,cn域名和特定网站直连(黑名单模式)</h1>
</div>

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


regexp:.*.cn.*,
regexp:.*hunau.*,
regexp:.*baidu.*,
regexp:.*delivery.mp.microsoft.*,
regexp:.*163.*,
regexp:.*chaoxing.*,
regexp:.*bing.*,
regexp:.*steamserver.*,
regexp:.*steamstatic.*,
regexp:.*dwai.life.*,
regexp:.*tearemix.*,


keyword:baidu,
keyword:cn,
keyword:hunau,
keyword:baidu,
keyword:delivery.mp.microsoft,
keyword:163,
keyword:chaoxing,
keyword:bing,
keyword:steamserver,
keyword:steamstatic,
keyword:dwai.life,
keyword:tearemix,



```


**正则表达式原理：**

1. **普通字符匹配**：正则表达式中的普通字符，比如字母和数字，会直接匹配字符串中的相应字符。

2. **元字符使用**：特殊字符或元字符，如 `.`、`*`、`?`、`+`、`^`、`$`、`[]`、`()`、`|` 等，在正则表达式中具有特殊意义，它们可以指定更复杂的匹配模式，如匹配任意字符、重复字符、可选字符等。

3. **模式组合**：通过组合上述普通字符和元字符，可以创建非常复杂的匹配模式，以识别特定的字符串模式，例如URL。

**匹配URL的正则表达式原理：**

- **起始和结束**：通常正则表达式以 `^` 开始表示行的起始，以 `$` 结束表示行的结束，确保整个字符串匹配URL格式。
- **协议**：使用 `(https?|ftp)` 等来匹配URL的协议部分，其中 `?` 表示前面的字符是可选的，匹配http或https。
- **域名**：使用 `[a-zA-Z0-9.-]` 来匹配域名中的合法字符，包括字母、数字、点和连字符。
- **端口**：使用 `(:\d{1,5})?` 来匹配端口号，`?` 表示端口是可选的。
- **路径、查询和片段**：使用 `(/[\w/:%#\$&\?\(\)~\.=\+\-]*)?` 等来匹配URL的路径、查询参数和片段。

**关键词匹配原理：**

关键词匹配通常是指在文本中搜索指定的单词或短语。这种匹配通常不使用正则表达式那样复杂的模式，而是简单的字符串查找。

- **完全匹配**：关键词通常要求完全匹配，即文本中的单词必须与搜索词完全一致。
- **大小写敏感**：关键词匹配可能区分大小写，也可能不区分，这取决于具体的搜索工具或函数设置。

**区别：**



## 谷歌搜索指令

- **精确搜索**: `"气候变化"`
  - 使用例子：搜索包含完整短语“气候变化”的页面。
- **排除词语**: `苹果 -电脑`
  - 使用例子：搜索与“苹果”有关，但不包含“电脑”的页面。
- **站点特定搜索**: `site:nytimes.com`
  - 使用例子：只显示来自纽约时报网站的搜索结果。
- **相关网站搜索**: `related:google.com`
  - 使用例子：查找与谷歌有类似内容的其他网站。
- **文件类型搜索**: `filetype:pdf`
  - 使用例子：查找PDF格式的文件。
- **数值范围搜索**: `电视 1000..2000元`
  - 使用例子：搜索价格在1000至2000元之间的电视。
- **定义搜索**: `define:哲学`
  - 使用例子：快速得到“哲学”的定义。
- **缓存搜索**: `cache:google.com`
  - 使用例子：显示谷歌网站的缓存版本。
- **全文搜索图书**: `intitle:全球变暖`
  - 使用例子：返回标题中含有“全球变暖”的网页。
- **通配符搜索**: `"成语 * 不到"`
  - 使用例子：搜索所有以“成语”开始并以“不到”结束的短语。
- **特定位置搜索**: `intext:环保`
  - 使用例子：找到所有正文中包含“环保”的页面。
- **搜索历史版本**: `inurl:forum 天文`
  - 使用例子：帮助你找到包含论坛讨论天文的页面。
- **搜索标题和网页正文**: `allintitle:气候 变化`
  - 使用例子：只显示标题中同时包含“气候”和“变化”的页面。
- **搜索锚文本**: `inanchor:"点击这里" 环保`
  - 使用例子：找到所有锚文本为“点击这里”且内容涉及环保的页面。
- **特定语言和地区搜索**: `lr:lang_ja` 和 `cr:countryJP`
  - 使用例子：分别搜索日语内容和来自日本的网页。
- **日期范围搜索**: `daterange:2458119-2458130`
  - 使用例子：搜索指定Julian日期范围内发布的页面。
- **搜索转换后的结果**: `convert: 10 miles to km`
  - 使用例子：将10英里转换成公里。
- **逻辑运算符**: `solar OR lunar`
  - 使用例子：搜索含有“solar”（太阳的）或“lunar”（月亮的）的页面。

```bash
ipconfig /flushdns

https://cf.trackerslist.com/best.txt
```
