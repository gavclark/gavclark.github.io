# this is a heading - edited in hackmd

## this is a heading 2

> this is a commented block
> which continues onto another line

* Unordered List Item #1
* Unordered List Item #2
* Unordered List Item #3

here is some DAX:
```
Revenue ALL = 
  CALCULATE(
      [Revenue],
      ALL(Sales)
  )
```

and here is some PowerQuery:
```
let
    Source = srcFolder,
    Content = Source{2}[Content],
    #"Imported Excel" = Excel.Workbook(Content),
    rlsSalespeople_Sheet = #"Imported Excel"{[Item="rlsSalespeople",Kind="Sheet"]}[Data],
    #"Promoted Headers" = Table.PromoteHeaders(rlsSalespeople_Sheet, [PromoteAllScalars=true]),
    #"Lowercased Text" = Table.TransformColumns(#"Changed Type",{ {"EmployeeEmail", Text.Lower, type text}, {"ManagerEmail", Text.Lower, type text}}),
    #"Added Custom" = Table.AddColumn(#"Lowercased Text", "Salesperson Name", each [FirstName] & " "&[LastName], Text.Type)
in
    #"Added Custom"
```

this seems to work so far

what about an image ?
![powerquery-folders-organised](https://user-images.githubusercontent.com/16735754/148458554-b7693893-6652-4bd3-a3af-55ec6f1028c3.png)




