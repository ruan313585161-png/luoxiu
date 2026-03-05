### 雪球网大V
```dataviewjs
const dvs = dv.pages('"03--大V跟踪/雪球网"').where(p => p.source);

let data = [];
for (let p of dvs) {
  const articles = dv.pages().filter(x => 
    x.file.name.contains(p.file.name) && 
    x.file.path != p.file.path
  );
  
  // 处理股票列表
  const stocks = p.stocks ? (Array.isArray(p.stocks) ? p.stocks.join(", ") : p.stocks) : "-";
  
  data.push({
    name: p.file.link,
    source: p.source,
    count: articles.length,
    fans: p.fans || "-",
    stocks: stocks
  });
}

data.sort((a, b) => Number(b.count) - Number(a.count));

const tableData = data.map(x => [x.name, x.source, x.count, x.fans, x.stocks]);
dv.table(["大V名称", "来源", "文章数", "粉丝数", "关注股票"], tableData);
```







### 抖音网大V
```dataviewjs
const dvs = dv.pages('"03--大V跟踪/抖音网"').where(p => p.source);
const data = dvs.map(p => {
  const articles = dv.pages().filter(x => 
    x.file.name.contains(p.file.name) && 
    x.file.path != p.file.path
  );
  return [p.file.link, p.source, articles.length];
});
dv.table(["大V名称", "来源", "文章数"], data);
```










