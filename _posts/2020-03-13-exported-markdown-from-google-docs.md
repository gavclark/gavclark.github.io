# This is the document and blog post title title - I wonder how that will work?


# This is a title of a blog post which I edited in google docs and converted to markdown (this is in heading #1 by the way)


## This particular line is in heading #2


### And this particular line is in heading #3

I am really interested to see :



* How all this converts to markdown
* Does this make my blogging process easier
* How does it integrate with GitHub
    * And is it easy to do things like this ?

This is a link to my github : [https://github.com/gavclark/gavclark.github.io](https://github.com/gavclark/gavclark.github.io)

And here’s a link to another [website](https://github.com/gavclark/gavclark.github.io) which is embedded in the text


<table>
  <tr>
   <td><strong>Column Heading #1</strong>
   </td>
   <td><strong>Column Heading #2</strong>
   </td>
   <td><strong>Column Heading #3</strong>
   </td>
  </tr>
  <tr>
   <td>Value 1
   </td>
   <td>Value 2
   </td>
   <td>Value 3
   </td>
  </tr>
  <tr>
   <td>Value 1-a
   </td>
   <td>Value 2-a
   </td>
   <td>Value 3-a
   </td>
  </tr>
</table>



---

Really interesting thing is if you can insert a code snippet ?


```
Revenue ALL = 
  CALCULATE(
      [Revenue],
      ALL(Sales)
  )
```


Here’s a longer code snippet in Power Query:


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


Wonder how it works if I have some different colour text how does that show up, maybe even some highlighted text to make a point

OK, so now an image (from google drive) will have to think about how I name them etc.

[https://drive.google.com/file/d/18oawf5u3SVc7pDzr7FUGdv4vUqyD-siQ/view?usp=sharing](https://drive.google.com/file/d/18oawf5u3SVc7pDzr7FUGdv4vUqyD-siQ/view?usp=sharing)

Let’s see how that works

One more for good luck 

[https://drive.google.com/file/d/1Zju2O8TtSqGGPC8OXe5wvAf5C4GwSTjr/view?usp=sharing](https://drive.google.com/file/d/1Zju2O8TtSqGGPC8OXe5wvAf5C4GwSTjr/view?usp=sharing)
