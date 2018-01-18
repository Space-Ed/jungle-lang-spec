
## Summary

Jungle is a language and toolchain for creating systems which brings new features above the standard constructs and paradigms of existing programming languages and data formats. 

it is intended to target many platforms, including web applications and servers. 

## Basic Principles

### Composability
    any system can be part of a larger system  

### Recoverability
    running program can be returned to a serial format at any time that can be recovered elsewhere to the same state.

### Declarative Linking
    the ability for relationships between components to be described in context which will automatically adapt to changing circumstances according to laws of implementation. 

### Dynamic Extensibility
    the ability to develop programs in place

### Observability
    changes to the structure of the program can be detected and reflected elsewhere


## Core Element Overview

To meet all of these requirements the data model of a program is a tree where each node is called a __cell__ which forms lateral connections through the use of __media__  __laws__ and __contacts__. The base class for all of these is called a __construct__ that is part of a composite pattern with the methods __patch__, __extract__ , __fetch__ and __notify__. A system as a whole, or any of its parts are __created__ within a __domain__ that system can also be __described__.


### Cell (@)

A cell is a kind of object which contains other constructs.
    a membrane which is host to contacts 
    a weave which is host to media and laws. 
    terminal/primative data
    head/meta data

In JGL a cell is described like

<@> cell-name :
    | meta-property : 
    data : 30,
    <+> contact-name :
        | in : (arg) => {

### Contact (+)

A contact represents a point of access to a cell similiar to a port or event stream or public method of a class, however a contact always has an inner and outer face, this adheres to the structural form of the membrane which has an inside and an outside. 

### Medium (~)

A medium represents a transport mechanism which provides the implementation of link creation and deletion between two types of contact (source and sink) provide the constraints for what links are possible. 

For example links could be basic data channels or perhaps audio/video streams or bidirectional protocols with specific fallback options.
 
### law (!)

A law represents a declaration of which contacts should be connected through which media, laws are able to designate individual contacts and entire groups of contacts through use of designator expressions (similar to glob patterns). a designator is not a one time selector but actually detects when new contacts meeting it are created.


## Construct methods

construct is the base node class of jungle it implements the terminal methods which are common to all things including data points, and composed cells and laws contacts and media.

### External Methods

#### init
    initialize the system by recursively walking the given description, this will populate the
#### dispose
    teardown the system recursively unlinking from the structure making ready for disposal 
#### patch 
    modify the structure to any degree of granularity and depth including the disposal and replacement 
#### extract
    inspect the structure to any degree of granularity
#### notify (outward)
    inform external watchers of changes occuring in the system 
#### fetch (outward)
    ask external source for determination of some part of the structure



