# jungle-lang (JGL) syntax

JGL is a language for specifying entire jungle systems 
- JungleJS (JGJS) is the extention to include enables value types that integrate specifically with javascript. 
- Jungle Markup Language (JGML) is the basic syntax only without top level language constructs

the language mixes elements from  XML, JSON and YAML:

it uses angular brackets like XML to give the element type, but does not use closing tags, instead opting for indentaion based contexts (Like YAML). 

Like in JSON key and value are seperated by a colon. but the same composite can have meta properties plus unique ids, anonymous and tagged children. 

## Language Constructs

### Values
```
[[value] =>
    [[number]]  
    [[string]]   
    [[regex]]   
    [[object]]  
    [[function]]
]

[[number]=>/\d*/]

```
### Properties
[[property] => 
    [Data Property]
    [ConstructProperty]
    [AnonymousProperty]
    [nullproperty]
    [headproperty]
### Data Property
> [[name]] : [[value]]
### Construct Property
```
<[[basis]]> [[name]] : [[value]]
```
### Anonymous Property
```
: [[value]]
```
### null valued property
```
[[name]] :
```
### default value property
```
<[[basis]]> [[name]]:
```
### Composition
```
<[[basis]]> [[name]] :
   [property] 
```

### Head/Meta Attributes
```
<[[name]]> [[name]] :
    | [=>[[name]] : [[value]]*]
```
### tagged names

```
<basis>-[[name]]-#-[[name]] [[name]]: 
```

## Core Jungle Syntax Extentions

### media

the builtin media of the jungle system are those regarding calls these media have a special symbol ~

extended media types will use <~basis> to 

_standard__
<~>

<~custom~>

<[[emmitter]] ~ [[reciever]] >

<

<[[emitter]]  ~ [[reciever]] ~ [[responder]]> [[name]] : 
    [[law-exp]*]

### law 

[[law-exp]=>
    [[designator]][[linker]][[designator]]
]

[[designator] =>
    [[d-term]...(.)]
]

[[linker] => ->]

[[d-term] => 
    ** 
    *  
    [name]
    [[d-term]][d-op][[dterm]]   // unassociative
    [[d-term]][d-op]([[dterm]]) // right associative
    ([d-term])[d-op][[dterm]]  // left associative 
]

[[d-op] => 
    &
    |
    
    
### contacts


### macros

A basis with a % character in it is a macro definition, as a top level definition it must have a name
its value is an interpretaion of the value passed to the 

<%> [[name]] : %


In macro context the provided value is usable as % and can be 
 - take only some fields (project)
 - insert into template
 - transform values with anonymous functions
 - inverse transform for recoverable

```
definition
<% [[name/*of target basis*/]]%> [[name (of basis)]]:
    %|hprop
    %:body
    %

### cells



### reference

### 
