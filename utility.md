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



