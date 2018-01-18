

## Formal Grammar Syntax

typically a language would be described using angle brackers <> to  indicate the grammatical expansions but because these symbols are part of the language we describe it using square brackets instead.

`[[type]]` 

for instance `[[name]]` stands for any valid identifier name

to define grammatical expansion

```
[[type] => 
    [subexpansion]
    jsregex
]
```

optional terms 
```
[[type]?]
```

multiple lines at same indentation
```
[[type]*]
```

multiple repitions with delimeter
```
[[line]...( )]
```

all spaces stand for any number of spaces except where it is between two expansions then there must be at least one space


