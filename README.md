# BibTeXLibrary
A utility library for BibTeX files written in C#.

## Ancestry
This library is based on the [BibTeXLibrary](https://github.com/BERef/BibTeXLibrary).  The library has been heavily modified and has had many additions so it can be used in an application for maintaining a BibTeX file.  It provides additional features as well as issue corrections.  As a result, it is no longer compatible with the original library.

## Usage at a glance
- string -> BibEntry
```csharp
var parser = new BibParser(
                new StringReader(
                  "@article{keyword, title = {\"0\"{123}456{789}}, year = 2012, address=\"PingLeYuan\"}"));
var entry = parser.GetAllResult()[0];
```

- BibEntry
```csharp
// Get Property
entry.Type;       // string: Article
entry.Title;      // string: 0{123}456{789}
entry["Title"];   // string: 0{123}456{789}
```

- BibEntry -> string
```csharp
entry.ToString();
// @Article{keyword,
//   title = {0{123}456{789}},
//   year = {2012},
//   address = {PingLeYuan},
// }
```

- Local File -> BibEntries
```csharp
var parser = new BibParser(new StreamReader("text.bib", Encoding.Default));
var entries = parser.GetAllResult();

foreach(var entry in entries) { ... }
```

## License
The MIT License (MIT)
Copyright (c) 2016 BERef

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
