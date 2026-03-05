---
source: 雪球网
url: https://xueqiu.com/u/9694162372
fans: "25516"
stocks:
  - 中钨高新
rating: ⭐(默认一星)
nickname: Egoistwow
---

### 全部观点
```dataview
TABLE without id
  file.link as 文件列表,
  split(file.name, "--")[0] as 股票或日期,
  split(file.name, "--")[1] as 大V,
  choice(
    length(split(file.name, "--")) = 3,
    split(file.name, "--")[2],
    split(file.name, "--")[3]
  ) as 观点
FROM "03--大V跟踪" OR "01--持仓股" OR "02--关注股"
WHERE contains(file.name, replace(this.file.name, ".md", ""))
WHERE file.name != this.file.name
SORT 日期 DESC
```