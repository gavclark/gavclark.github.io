---
title: "This is the blog post title from frontmatter"
excerpt: "This is a bit more detail about the blog post and why you should read it "
tags: ["DAX", "PowerQuery", "Power BI"]
---
# This is my blog post from typora

# Another heading 1

# this is a heading 1
## this is a heading 2 
### this is a heading 3
#### This is a heading 4
##### this is a heading 5
###### this is a heading 6

this is just some general paragraph text

> quoted block - really there should be some way that this quote line wraps when you have a lot to say but I am not 100% sure that is the way that it works. Maybe you need the right words to put in it ?

1. ordered list #1
2. ordered list #2

here's some more text

what about just pasting in the image ?


![powerquery-folders-organised](https://user-images.githubusercontent.com/16735754/148005665-8ef61014-12a1-452f-9822-36e088174fe0.png)

now try some syntax highlighting (DAX first)

```dax
Revenue ALL = 
  CALCULATE(
      [Revenue],
      ALL(Sales)
  )
```
not sure why the prism highligting isn't working ? at least there's some basic stuff there

and now some PowerQuery
```powerquery
{% raw %}
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
{% endraw %}
```

hoping that all worked, if so I'm ready to start blogging ?!
