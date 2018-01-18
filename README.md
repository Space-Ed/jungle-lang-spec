# Jungle System Description Language (JGL)

the jungle system description language is a data serialization format with optional embedded scripting, it is intended for use on many different platforms through the use of transpilers and compilers. For instance the jungle-js framework(Node.js and web implementation) requires domains to be described with JavaScript files and recoverable systems to be described with JSON serializable structures. 

The purpose of this repository is not to dictate any output formats but to provide enough information that a conformant implementation could be built in whatever language for whatever runtime. 

To be a conformant implementation requires a certain minimal requirements to be met, and further if certain features are implemented they must be explicitly implemented to meet an extended specification.

## Contents

### [Introduction](introduction.md)
learn about Jungles aims and basic concepts 
    - [principles](introduction.md#Basic Principles)
    - [core elements](introduction.md#Core Element Overview)
    - [core methods](introduction.md#Construct Methods)

### [Interpretation](interpretation.md)
how to read the specification
    - [Versions]()
    - [Formal Grammar Syntax]()

### [OS level utilities](utility.md)
description of the jg cli tool, configuration and jungle system process 
    - [Fountational](utility.md#Foundational)
        - `jg init`
    - [Extended](utilitiy.md#extended.md)

### [Syntax](syntax.md)
    - [Different types](syntax.md)
    - [Serialization Format](syntax.md)
    - [System Description](syntax.md)

### Behaviour
this section describes the expected behaviour of a jungle system which is described using the JGL syntax
    - [Foundational](behaviour-foundation.md)
    - [Extended](behaviour-extended.md)

### Standard Library
   - a platform which implements interfaces to common underlying systems (like the file system or TCP sockets) should be use consistent with other implementations. So here we describe the standard library. 

### Specification Tests
a body of language agnostic specifications against the targets. 

### Implementations

the only implementation guide is that of the


Copyright (c) Edward Dalley 2018

