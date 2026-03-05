 观点汇总
```dataview
TABLE 
  regexreplace(file.name, ".*--", "") as 观点,
  split(file.name, "--")[1] as 作者,
  split(file.name, "--")[2] as 日期
WHERE contains(file.name, "京东方A")
WHERE file.name != this.file.name
SORT 日期 DESC
```

### 筛选看涨
```dataview
LIST
WHERE contains(file.name, "京东方A") 
WHERE regexreplace(file.name, ".*--", "") = "看涨"
SORT file.name DESC
```