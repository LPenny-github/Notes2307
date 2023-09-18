# partial match VS. perfect match

Sometimes it will be called `first match` and `whole match`.

## example

There are two candidates: (A) `"10 apples"` (B) `"apple"` .

And there are three kinds of regular expression requirements: (1) `/.*ap.*/` (2) `/ap.*/` (3) `/^ap.*/`

|(requirements) |partial |perfect |
|---------------|--------|--------|
|(1) `/.*ap.*/` |(A)&ensp;(B) |(A)&ensp;(B)
|(2) `/ap.*/`   |(A)&ensp;(B) |&emsp;&emsp;(B)
|(3) `/^ap.*/`  |&emsp;&emsp;(B) |&emsp;&emsp;(B)

In the `perfect match` mode, the requirement will be automatically add `^` at the beginning and `$` at the end of the line, and therefore (2) `/ap.*/` will be executed like `/^ap(.*)$/` .