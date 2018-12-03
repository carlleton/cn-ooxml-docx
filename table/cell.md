# 单元格
表格单元格包含表格内容，由`<w:tc>`元素指定。表格单元格必须包含至少一个块级元素，即使它是空的`<p />`。单元格可以包含任何块级内容，包括嵌套的段落和表格。
```
<w:tc>
  <w:tcPr>
    <w:tcW w:w="2880" w:type="dxa"/>
  </w:tcPr>
  <w:p>
    <w:r>
      <w:t>AAA</w:t>
    </w:r>
  </w:p>
</w:tc>
```
_**参考：** ECMA-376，第3版（2011年6月），基础和标记语言参考§17.4.66。_

## Word 2007示例
![](http://officeopenxml.com/images/wp-tableCell-1.gif)

## 内容
`<w:tc>`元素可包含大量的元素，通常与跟踪修订和自定义的XML相关。主要的元素如下：

|元素|描述|
|---|---|
|p|指定单元格的内容段落请参阅[段落](http://officeopenxml.com/WPparagraph.php)。<br>_**参考：** ECMA-376，第3版（2011年6月），基础和标记语言参考§17.3.1.22。_|
|tbl|将表指定为单元格的内容。请参阅[表](http://officeopenxml.com/WPtable.php)<br>_**参考：** ECMA-376，第3版（2011年6月），基础和标记语言参考§17.4.38。_|
|tcPr|指定要应用于当前单元格的属性。此类属性会覆盖冲突的表或行属性。请参见[表格单元属性](http://officeopenxml.com/WPtableCellProperties.php)。<br>_**参考：** ECMA-376，第3版（2011年6月），基础和标记语言参考§17.4.70。_|

## 属性
`<w:tc>`元素可以包含一个属性

|属性|描述|
|---|---|
|id|指定单元的唯一标识符。它必须在表中是唯一的，并且用于使用headers元素将单元格标识为表中其他单元格的标题单元格。例如，`<w:tc w:id="januaryeight">`。|


# 对应HTML/CSS属性：
`<td>AAA</td>`