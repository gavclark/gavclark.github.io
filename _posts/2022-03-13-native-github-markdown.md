---
title: "This is the blog post title from frontmatter"
excerpt: "This is a bit more detail about the blog post and why you should read it "
tags: ["#gtbr", "Get the Basics Right", "Power BI"]
---
# this is the blog post title which should be in heading number 1

# this is heading 1
## this is heading 2
### this is heading 3
#### this is heading 4

this is just some normal text

a list that is not ordered
- this is item 1
- this is item 2
- this is item 3

a list that is ordered
1. this is item 1
2. this is item 2
3. this is item 3

> quoted block - really there should be some way that this quote line wraps when you have a lot to say but I am not 100% sure that is the way that it works. Maybe you need the right words to put in it ? we could keepy typing and assuming it will just keep wrapping the words around
> but if you press return it will continue to mark as a quoted block - but is it in the same quote



```
Revenue ALL = 
  CALCULATE(
      [Revenue],
      ALL(Sales)
  )
```

and some longer PowerQuery stuff
```
let
    Source = srcFolder,
    Content = Source{2}[Content],
    #"Imported Excel" = Excel.Workbook(Content),
    rlsSalespeople_Sheet = #"Imported Excel"{[Item="rlsSalespeople",Kind="Sheet"]}[Data],
    #"Promoted Headers" = Table.PromoteHeaders(rlsSalespeople_Sheet, [PromoteAllScalars=true]),
    #"Changed Type" = Table.TransformColumnTypes(#"Promoted Headers",{{"EmployeeID", Int64.Type}, {"FirstName", type text}, {"LastName", type text}, {"ManagerID", Int64.Type}, {"EmployeeEmail", type text}, {"ManagerEmail", type text}, {"ManagerLevel", Int64.Type}, {"IsManager", Int64.Type}}),
    #"Lowercased Text" = Table.TransformColumns(#"Changed Type",{{"EmployeeEmail", Text.Lower, type text}, {"ManagerEmail", Text.Lower, type text}}),
    #"Added Custom" = Table.AddColumn(#"Lowercased Text", "Salesperson Name", each [FirstName] & " "&[LastName], Text.Type)
in
    #"Added Custom"
```

does this support ::highlighting:: and ~~strikethrough~~ , looks like for some yes

OK upload an image:

![powerquery-folders-organised](https://user-images.githubusercontent.com/16735754/158059642-9921ca20-78d0-4df5-a2f0-92d6aa652a59.png)

and a data model one just for completeness

![power bi data model](https://user-images.githubusercontent.com/16735754/158059666-2b051e5e-e3da-4c6d-a60b-fd751ada2c89.png)