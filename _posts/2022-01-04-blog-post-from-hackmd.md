# this is a heading - edited in hackmd

## this is a heading 2

> this is a commented block
> which continues onto another line

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



