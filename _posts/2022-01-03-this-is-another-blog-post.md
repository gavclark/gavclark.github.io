# This is my blog post from typora

## this is a heading 2 

this is just some general paragraph text

> quoted block

1. ordered list #1
2. ordered list #2

here's some more text

what about just pasting in the image ?


![powerquery-folders-organised](https://user-images.githubusercontent.com/16735754/148005665-8ef61014-12a1-452f-9822-36e088174fe0.png)

now try some syntax highlighting (DAX first)

```DAX
Revenue = SUM(Sales[SalesValue])
```

and now some PowerQuery

```PowerQuery
let
    Source = srcFolder,
    Content = Source{2}[Content],
    #"Imported Excel" = Excel.Workbook(Content),
    rlsSalespeople_Sheet = #"Imported Excel"{[Item="rlsSalespeople",Kind="Sheet"]}[Data],
    #"Promoted Headers" = Table.PromoteHeaders(rlsSalespeople_Sheet, [PromoteAllScalars=true]),
    #"Lowercased Text" = Table.TransformColumns(#"Changed Type",{{"EmployeeEmail", Text.Lower, type text}, {"ManagerEmail", Text.Lower, type text}}),
    #"Added Custom" = Table.AddColumn(#"Lowercased Text", "Salesperson Name", each [FirstName] & " "&[LastName], Text.Type)
in
    #"Added Custom"
```

hoping that all worked, if so I'm ready to start blogging ?!
