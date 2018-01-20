
Domains being defined with the same format as a system, even the root domain, gives us an interesting problem
we have already found that the best way to import a domain is often through a mount point. That is the entry point. 

The Boot Domain is an idea that the constructs used to define a domain are accessible in a context. THe boot domain is the jungle kernel. and it certainly wont change over the course of an application. the root domain is not based on the boot domain.

the root domain is the domain where entities are constructed, it by default must contain the minimal set of entities to define a structure.

It seems odd to have this overarching system which maps virtually one to one onto the operative system.
 
The Composite and The Domain. 
The Construct and Description.
The link and dependency.
the extract and the schema
the notify and the update
the patch and the definition
the fetch and the poll



In a sense they have been seperate to preserve some relationships which are not 

A domain on another domain is not a child of that, it extends from it, but is not referrable from it, 

A domain is passed into the decendent 

domain has blending of descriptions
 
domain can create constructs

domain can describe constructs

the boot domain is a domain with the minimum entries required to define domains.
The core domain is a domain with all the basic constructs and invariant imports it is a composite in the boot domain
the root domain is a domain with all imports and app specific constructs, is is based on the core domain. it is a composite operating in the boot domain
the main construct is a construct operating in the root domain it is the app.

## Boot Process

Define Domain

Create Boot Domain populated with
- import
- define
- base
- sub
- macro

Load Core within boot domain loading from core.js

Create Root Domain based on Core within boot loading from root.jgd file

Create main construct within Root Domain loading from main.jgc file

the parsing of .jgd and .jgc files is implicit. These two files both have the same syntax, the indication is that a domain file is a construction of the boot domain, where the .jgc files are of the domain that they live next to.

some parsing of jgd will create statements ( imports / js scope import ) that are required to be static. this is even for the root domain, if contacts performing certain functions are added to the domain, these additions cannot be changed. This makes it difficult to have this file as a dynamic space for definition. patching the root domain from a client, is potentially going to replace code-blocks. 

Why must they be static? once code is loaded you cant unload it, references to a global variable cannot be refreshed automatically when that variable is changed. you could scan all references from jsscopes to it and update the users of those scopes.



ultimately changes to a domain, could be intended for entirely new entities, 


Versioning

if a new version of a Nature or Description under a certain name is published, the entities that are based on that should potentially be updated. The other possible behaviour is that they are now branched and hence will not update. Somewhere in the middle is the semantic versioning style and the manual fast forward update style.

The fact that the receiver and publisher could both make dictations about what style of update is required or supported means that inconsistencies can occur between the entities and the domains. 

for instance I may say that all entries must accept updates.



One strategy is to say that no restrictions can be made, that is either push only or pull only
another strategy is to say  

another strategy is to say there are no updates to existing entities. To update you must destroy and remake, which would be the case anyway but without push updates you would need to visit every dirty node and reset it (or reset root).

the language does not dictate the strategy used, in any case it will not be an exposed port.. or
to update from the perspective of an entity you must send a trigger to a particular place.

One particularly elegant system is one where all instances are synchronized by the domain being a listener to all constructs constructed in it. thereby as soon as a change occurs, the same change is applied to all other instances and the prototype.

this model operates on the assumption that all of these instances are homogenous, that if a change can be affected in one place, that it will be affected in all places.

there is a neccessity to instanciate synchronized and branched. But effectively synchronized just means that there is shared state. It gets really hard when you want to share over asynchronous spaces. That stems from the notion of a remote domain.


Previously we considered synchronization as moving through the notify and being managed by an agent in a higher context. now we consider it to be in a transcendent context ( the domain ) it would also require that level to create a domain extention modelled on a construct. 

<$base$> synchronized: value
