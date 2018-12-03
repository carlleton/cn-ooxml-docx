# 单元格
表格规定一个单元格元素`<table:table-cell>`包含在一个行元素`<table:table-row>`中
_**参考：**Office应用程序的打开文档格式版本1。2（2011年5月）§9.1.4。_
```
<table:table table:name="Table1" table:style-name="Table1">
  <table:table-column table:style-name="Table1.A" table:number-columns-repeated="3"/>
  <table:row>
    <table:table-cell table:style-name="Table1.A1" office:value="string">
      <text:p text:style-name="Table_20_Contents">AAA</text:p>
    </table:table-cell>
    . . .
  <table:row>
  . . .
</table:table>
```
## 属性
最常用的属性如下：

|属性|描述|
|---|---|
|table:number-columns-spanned|指定单元格跨越的列数。注意，当值大于1时，`<table:covered-table-cell>`必须出现在表中以表示覆盖的单元格。|
|table:number-rows-spanned|指定单元格跨越的行数。注意，当值大于1时，`<table:covered-table-cell>`必须出现在表中以表示覆盖的单元格。|
|table:style-name|指定单元格的样式。|
|table:number-columns-repeated|指定重复单元格的连续列数|

## 内容
最常用的元素如下。

|元素|属性|
|---|---|
|`<table:table>`|指定表。|
|`<text:h>`|指定标题。|
|`<text:list>`|指定列表。|
|`<text:numbered-paragraph>`|指定编号的段落。|
|`<text:p>`|指定段落。|
|`<text:section>`|指定一个章节。|
|`<text:table-of-content>`|指定目录。|