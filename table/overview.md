# 表格结构
表由行和单元格组成，其结构与HTML表格非常相似。它由`<w：tbl>`元素定义。
```
<w:tbl>
  <w:tblPr>
    <w:tblStyle w:val="TableGrid"/>
    <w:tblW w:w="5000" w:type="pct"/>
  </w:tblPr>
  <w:tblGrid>
    <w:gridCol w:w="2880"/>
    <w:gridCol w:w="2880"/>
    <w:gridCol w:w="2880"/>
  </w:tblGrid>
  <w:tr>
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
    <w:tc>
      <w:tcPr>
        <w:tcW w:w="2880" w:type="dxa"/>
      </w:tcPr>
      <w:p>
        <w:r>
          <w:t>BBB</w:t>
        </w:r>
      </w:p>
    </w:tc>
    <w:tc>
      <w:tcPr>
        <w:tcW w:w="2880" w:type="dxa"/>
      </w:tcPr>
      <w:p>
        <w:r>
          <w:t>CCC</w:t>
        </w:r>
      </w:p>
    </w:tc>
  </w:tr>
  . . .
</w:tbl>
```
>注意：当具有相同样式的两个相邻表一起存在而没有任何插入`<w：p>`元素时，表将被视为单个表。

*参考：ECMA-376，第3版（2011年6月），基础和标记语言参考§17.4.38*

### Word 2007 示例:
![](http://officeopenxml.com/images/wp-table-1.gif)

## 内容
一个`<w:tbl>`元素可以包含大量元素，主要与跟踪修订和添加自定义XML相关。核心要素如下所示：

| 元素 | 说明 |
| ------ | ------ |
| tblGrid | 指定表的列。<br>请参考[表格列](http://officeopenxml.com/WPtableGrid.php)*参考：ECMA-376，第3版（2011年6月），基础和标记语言参考§17.4.49。* |
|tblPr|指定表的表范围属性。这些属性可以由单个表级异常，行和单元级属性覆盖。请参见[表格属性](http://officeopenxml.com/WPtableProperties.php)。<br>*参考： ECMA-376，第3版（2011年6月），基础和标记语言参考§17.4.60。*|
|TR|指定表行。见表格[表行](http://officeopenxml.com/WPtableRow.php)。<br>*参考： ECMA-376，第3版（2011年6月），基础和标记语言参考§17.4.79。*|


-------------------------------------------------------------------------
# 对应HTML/CSS属性：
```
<table style="width:100%;">
  <tr>
    <td>AAA</td>
    <td>BBB</td>
    <td>CCC</td>
  </tr>
  . . .
</table>
```
**HTML / CSS示例：**

|AAA|BBB|CCC|
|---|---|---|
|DDD|EEE|FFF|
|GGG|HHH|III|
