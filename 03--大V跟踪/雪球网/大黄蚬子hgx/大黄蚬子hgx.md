---
source: 雪球网
url: https://xueqiu.com/u/3045778209
fans: "171948"
stocks:
  - 京东方A
  - 兴业银锡
  - 紫金矿业
  - 铜陵有色
rating: ⭐⭐⭐
nickname: 大黄蚬子hgx
---


### 全部观点
```dataview
TABLE 
  regexreplace(file.name, "--.*", "") as 股票,
  regexreplace(file.name, ".*--(\\d{4}年\\d{1,2}月\\d{1,2}日)--.*", "$1") as 日期,
  regexreplace(file.name, ".*--", "") as 观点评级
WHERE contains(file.name, "大黄蚬子hgx")
WHERE file.name != this.file.name
SORT 日期 DESC
```

### 筛选看涨
```dataview
LIST
WHERE contains(file.name, "大黄蚬子hgx") 
WHERE regexreplace(file.name, ".*--", "") = "看涨"
SORT file.name DESC
```

```dataview
TABLE source, nickname, fans
FROM "03--大V跟踪"
WHERE file.name = "大黄蚬子hgx"
```