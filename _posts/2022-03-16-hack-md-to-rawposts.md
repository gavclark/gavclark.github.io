# hack md block post with update of github

## this is heading 2
### heading 3
#### 4 you get the idea
##### 5 , yes - even smaller



| Column 1 | Column 2 | Column 3 |
| -------- | -------- | -------- |
| Value a  | Value B  | Value C  |

![](https://i.imgur.com/V904DjX.png)


## let's try some DAX code ....

```dax
Cumulative Revenue = 
var __LastSaleDate = MAX(Sales[OrderDate])
RETURN
CALCULATE(
    [Revenue],
    FILTER(
         ALLSELECTED('Calendar'[Date]),
         'Calendar'[Date] <= __LastSaleDate
         )
    )
```
## and now some PowerQuery
{% raw %}
```powerquery
let
    Source = Csv.Document(File.Contents("C:\Users\gavcl\OneDrive\Power_BI_Data\PBI_Labs_SalesTransactionDatav2.csv"),[Delimiter=",", Columns=13, Encoding=1252, QuoteStyle=QuoteStyle.None]),
    #"Promoted Headers" = Table.PromoteHeaders(Source, [PromoteAllScalars=true]),
    #"Changed Type" = Table.TransformColumnTypes(#"Promoted Headers",{{"TransactionID", Int64.Type}, {"CustomerID", Int64.Type}, {"OrderDate", type date}, {"Sales Qty", Int64.Type}, {"SalesCost", type number}, {"SalesValue", type number}, {"SalesPersonID", Int64.Type}, {"DaysSinceInitialContact", Int64.Type}, {"ProductID", Int64.Type}, {"SalesChannel", type text}, {"Date 01", type text}, {"Date 02", type text}, {"Date 03", type text}}),
    #"Split Column by Delimiter" = Table.SplitColumn(#"Changed Type", "Date 01", Splitter.SplitTextByEachDelimiter({" "}, QuoteStyle.Csv, false), {"Date 01.1", "Date 01.2"}),
    #"Changed Type1" = Table.TransformColumnTypes(#"Split Column by Delimiter",{{"Date 01.1", type date}, {"Date 01.2", type time}}),
    #"Split Column by Delimiter1" = Table.SplitColumn(#"Changed Type1", "Date 02", Splitter.SplitTextByEachDelimiter({" "}, QuoteStyle.Csv, false), {"Date 02.1", "Date 02.2"}),
    #"Changed Type2" = Table.TransformColumnTypes(#"Split Column by Delimiter1",{{"Date 02.1", type date}, {"Date 02.2", type time}}),
    #"Split Column by Delimiter2" = Table.SplitColumn(#"Changed Type2", "Date 03", Splitter.SplitTextByEachDelimiter({" "}, QuoteStyle.Csv, false), {"Date 03.1", "Date 03.2"}),
    #"Changed Type3" = Table.TransformColumnTypes(#"Split Column by Delimiter2",{{"Date 03.1", type date}, {"Date 03.2", type time}}),
    #"Renamed Columns" = Table.RenameColumns(#"Changed Type3",{{"Date 01.1", "Invoice Date"}, {"Date 02.1", "Payment Date"}, {"Date 03.1", "Retention Period"}, {"SalesCost", "Sales Cost"}, {"SalesValue", "Sales Value"}, {"SalesChannel", "Sales Channel"}}),
    #"Removed Other Columns" = Table.SelectColumns(#"Renamed Columns",{"TransactionID", "CustomerID", "OrderDate", "Sales Qty", "Sales Cost", "Sales Value", "SalesPersonID", "DaysSinceInitialContact", "ProductID", "Sales Channel", "Invoice Date", "Payment Date", "Retention Period"})
in
    #"Removed Other Columns"
```
{% endraw %}

![](https://i.imgur.com/YM8BgTB.png)


