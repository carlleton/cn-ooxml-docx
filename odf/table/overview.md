# 表格结构
在ODF格式中明确定义了表格使用`<table:table>`元素，一个表格元素包含行和列。行被分成单元格，并且通过在行内获取具有相同位置的所有单元格来暗示列。表可以出现在`<office：text>`中，一个单元格内，页眉或页脚中，或者其他

_**参考：**Office应用程序的打开文档格式版本1。2（2011年5月）§9.1.2。_
```
<table:table table:name="Table1" table:style-name="Table1">
  <table:table-column table:style-name="Table1.A" table:number-columns-repeated="3"/>
  <table:row>
    <table:table-cell table:style-name="Table1.A1" office:value="string">
      <text:p text:style-name="Table_20_Contents">AAA</text:p>
    </table:table-cell>
    <table:table-cell table:style-name="Table1.A1" office:value="string">
      <text:p text:style-name="Table_20_Contents">BBB</text:p>
    </table:table-cell>
    <table:table-cell table:style-name="Table1.C1" office:value="string">
      <text:p text:style-name="Table_20_Contents">CCC</text:p>
    </table:table-cell>
  <table:row>
  . . .
</table:table>
```
## 属性
最常见的属性如下：

|属性|描述|
|---|---|
|table:name|指定唯一名称。|
|table:style-name|指定表的表样式。|
|xml:id|指定唯一ID，并由W3C（xml-id）标准化。|
|table:protected|指定表是否受保护，以便用户无法对其进行编辑。值是*真和假*。|

## 内容：
最常见的元素如下：

|元素|描述|
|---|---|
|&lt;table:table-column&gt;|指定一个或多个相邻列的属性。|
|&lt;table:table-column-group&gt;|组相邻列|
|&lt;table:table-columns&gt;|包含`<table：table-column>`元素组，当表跨越页面时不会重复这些元素。|
|&lt;table:table-header-columns&gt;|表示列标题。|
|&lt;table:table-header-rows&gt;|表示行标题。|
|&lt;table:table-row&gt;|代表一行。|
|&lt;table:table-row-group&gt;|将相邻行的组分组，而不显示为表头。|
|&lt;table:table-rows&gt;|包含`<table：table-row>`元素组，当表跨越页面时不会重复这些元素。|
|&lt;table:title&gt;|指定表的标题。|