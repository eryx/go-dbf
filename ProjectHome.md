This project is a part of go-shp library. go-shp is a pure Go implementation of Esri Shapefile format.

You can incorporate the library into your local workspace with the following 'go get' command:

```
go get code.google.com/p/go-dbf/godbf
```

Code needing to call into the library needs to include the following import statement:
```
import (
  "code.google.com/p/go-dbf/godbf"
)
```

There's no real documentation as yet. Here is a very simple snippet of example 'load' code to get you going:
```
  dbfTable, err := godbf.NewFromFile("exampleFile.dbf", "UTF8")

  exampleList := make(ExampleList, dbfTable.NumberOfRecords())

  for i := 0; i < dbfTable.NumberOfRecords(); i++ {
    exampleList[i] = new(ExampleListEntry)

    exampleList[i].someColumnId, err = dbfTable.FieldValueByName(i, "SOME_COLUMN_ID")
  }

```

Note:

  * You must have [Mercurial](http://mercurial.selenic.com/) installed for the go get command to work.