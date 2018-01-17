This file is a draft language specification for jungle script (JGS .jg) and jungle markup (JGML .jgml) languages


# JGML versus JGS

JGS is the static description of a jungle environment, it is all the parts that are compiled in and are run once at program boot. while an interpreter environment can extend the domain 

JGDL compiles to javascript or the appropriate language for the target platform it is a superset of JGML which also allows for javascript code to be embedded in functional closure syntax. Also it allows for the importing of javascript 

JGML is a data format which defines the structure and relationships of a system in a single object, that is the file will compile to a single object. It is possible to compile to JSON or to an exported javascript object.


## Running Jungle

A jungle process takes a .jg file to define it's domain and a .jgml file to instantiate the program.
the progressive extention of a domain by dynamic composition is enabled by creation of JGML files that can be defined.

### Usage example

$ jg run -t node domain.jg  // start a new jungle process locally 
Jungle version: 1.3.4 
Created new Jungle instance on platform Node.js

$ jg patch -f main.jgml
Successfully patched

$ jg describe
```
<cell> root : 
    < renderer :: HTMLStatic> view:
    	<div> :
	    <h> : hello world

    < server :: Net > server :
	    | port : 3040

    < route :: Net > router :
    	server -> renderer.render
```

```
$ jgc -t web domain.jg --root main.jgml --out client.js
```

transpile JGS && JGML to JS and create a bundled file that boots the app
```
-t : target platform : every target platform has a toolchain to either load the files or compile to the deployable artefact
 --root : root structure : the seed for the program structure that will be recovered
 --out : emit file    : the deployable object for the platform
```
### Project Directory Contents

A repository containing a jungle project will have a configuration file which can determine

- what targets are available 
- what dependencies
- what port to run admin clients
- what build options to use

running a target local from source files will cache the compiled files in .jungle


## Jungle User Agents

the a jungle system is a live structure which can be connected to from management clients.
There is a client for each possible task, each using a Socket/tty connection.

### On the structure
__examine__ the program to any degree of detail including entirety (emits JGML to stdout)
__patch__    the program (opens editor and parses JGML from saved file OR loads a file/stdin)
__listen__   to changes occurring at any position in structure (create client that emits updates of JGML) 
be __prompt__ed to describe a position in the structure that is unfilled  (client program that gives you an editor to define requested data, in a queue)

### On the Domain
list possible constructions of a domain (output basis names)
extend a domain with a new definition JGML
extract a domain supplement

## Root agent
jungle run is a client at the level of the root, it performs the initial domain bootstrapping, supplement and creation of the root structure.
if run interactively the root client (interactive within the jungle process itself) can only do one thing at a time 

## Interactive Clients

### Located Clients
single command clients do not have the ability to move / be located, movement is achieved by simply having an interactive client that nests command argument and reponses to it's own remembered position. This is not core functionality, an interactive client is responsible for managing the many connections it could have active.

### Types of Interactive
a client could be a web interface inspecting the structure or a program managing the persistance of the structure. To have some accountability with patches, identities could be used, essentially that requires configuration of the jungle global config options (for local instance)

$ jungle login user@host:port
sets the current target for jungle commands, not interactive, or depending on the nearest jungle file.

or using a ssl token issue to a user that has provided a password. (passwords not managed by jungle)

## Syncrhonized Clients

It is possible to arrange the foundational clients such that notifications go to patches and fetches to extracts enabling a cycle of updates between two structures.


## Many instances

To create many instances of applications you would need to compile the project to the host operating system and thereby export a project directory that assigns its own unique Port. 

# JGML

JGML is a language for specifying entire jungle systems both JGS and JGML share the same syntax, JGS enables value types that integrate specifically with javascript. 

it may look like a strange 3 way child of XML, JSON and YAML, it uses angular brackets like XML to give the type, but does not use closing tags, instead opting for indentaion based depth escaping (Like YAML). Like in JSON key and value are seperated by a colon. 

to indicate a gramatical expansion of that type we give the possible expansions as distinct lines


```[[Type]]
``` 

to define grammatical expansion of type

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
