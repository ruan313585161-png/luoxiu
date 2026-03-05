---
source: 雪球网
url: https://xueqiu.com/u/8699572373
fans: "12592"
stocks:
  - 内蒙华电
  - 晋控煤业
rating: ⭐(默认一星)
---
### 全部观点
```dataview
TABLE 
  regexreplace(file.name, "--.*", "") as 股票,
  regexreplace(file.name, ".*--(\\d{4}年\\d{1,2}月\\d{1,2}日)--.*", "$1") as 日期,
  regexreplace(file.name, ".*--", "") as 观点评级
WHERE contains(file.name, "Bruce-lim")
WHERE file.name != this.file.name
SORT 日期 DESC
```


