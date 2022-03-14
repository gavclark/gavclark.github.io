# another blog post created in hackmd

[ToC]

# this is heading 1
## this is heading 2
### this is heading 3
#### this is heading 4
##### this is heading 5
###### this is heading 6

interesting that you can get emoji's :pushpin: as well as ==highlighting some text too== it is seems really good :+1: 

###### tags: `Tag(PowerQuery)`

> This note is yours, feel free to play around.  :video_game: 
> Type on the left :arrow_left: and see the rendered result on the right. :arrow_right: 

## :memo: Where do I start?

### Step 1: Change the title and add a tag

- [x] Create my first HackMD note (this one!)
- [ ] Change its title
- [ ] Add a tag

:rocket: 

![Power BI Data Model](https://i.imgur.com/M9QzPhn.png)

![](https://i.imgur.com/AczUQHy.png)

let's try a DAX code window:
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

and will also try some PowerQuery:
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

### Step 2: Write something in Markdown

Let's try it out!
Apply different styling to this paragraph:
**HackMD gets everyone on the same page with Markdown.** ==Real-time collaborate on any documentation in markdown.== Capture fleeting ideas and formalize tribal knowledge.

- [x] **Bold**
- [ ] *Italic*
- [ ] Super^script^
- [ ] Sub~script~
- [ ] ~~Crossed~~
- [x] ==Highlight==



:::info
:bulb: **Hint:** You can also apply styling from the toolbar at the top :arrow_upper_left: of the editing area.

![](https://i.imgur.com/Cnle9f9.png)
:::

> Drag-n-drop image from your file system to the editor to paste it!

### Step 3: Invite your team to collaborate!

Click on the <i class="fa fa-share-alt"></i> **Sharing** menu :arrow_upper_right: and invite your team to collaborate on this note!

![permalink setting demo](https://i.imgur.com/PjUhQBB.gif)

- [ ] Register and sign-in to HackMD (to use advanced features :tada: ) 
- [ ] Set Permalink for this note
- [ ] Copy and share the link with your team

:::info
:pushpin: Want to learn more? ➜ [HackMD Tutorials](https://hackmd.io/c/tutorials) 
:::

---

## BONUS: More cool ways to HackMD!

- Table

| Features          | Tutorials               |
| ----------------- |:----------------------- |
| GitHub Sync       | [:link:][GitHub-Sync]   |
| Browser Extension | [:link:][HackMD-it]     |
| Book Mode         | [:link:][Book-mode]     |
| Slide Mode        | [:link:][Slide-mode]    | 
| Share & Publish   | [:link:][Share-Publish] |

[GitHub-Sync]: https://hackmd.io/c/tutorials/%2Fs%2Flink-with-github
[HackMD-it]: https://hackmd.io/c/tutorials/%2Fs%2Fhackmd-it
[Book-mode]: https://hackmd.io/c/tutorials/%2Fs%2Fhow-to-create-book
[Slide-mode]: https://hackmd.io/c/tutorials/%2Fs%2Fhow-to-create-slide-deck
[Share-Publish]: https://hackmd.io/c/tutorials/%2Fs%2Fhow-to-publish-note

- LaTeX for formulas

$$
x = {-b \pm \sqrt{b^2-4ac} \over 2a}
$$

- Code block with color and line numbers：
```javascript=16
var s = "JavaScript syntax highlighting";
alert(s);
```

- UML diagrams
```sequence
Alice->Bob: Hello Bob, how are you?
Note right of Bob: Bob thinks
Bob-->Alice: I am good thanks!
Note left of Alice: Alice responds
Alice->Bob: Where have you been?
```
- Auto-generated Table of Content
[ToC]

> Leave in-line comments! [color=#3b75c6]

- Embed YouTube Videos

> Put your cursor right behind an empty bracket {} :arrow_left: and see all your choices.

- And MORE ➜ [HackMD Tutorials](https://hackmd.io/c/tutorials)
