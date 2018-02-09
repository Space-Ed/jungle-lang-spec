

functional composition is acheived in a few ways

-  by tying together fnctions by using the output of one to the input of another, known as currying or piping.
- function valued argument, that is one function is the user of another by having it provided with it's invokation. this is known as first-order functions (as a value)  or higher order functions (has function argument). 
- function valued return, one function produces another, could be called a factory or higher order function.
- functions are referred to and called through an exposed name in the scope

the jungle way is to unify function representation and data representation. The current means of defining a contact, is to provide the terminal function composed in the above ways, meaning we must import external faculties somehow like embedded js scopes and the like. Ideally we could analyse the true objective of functions and thereby create a language using the same jungle format.

the creation of an arbitrary function requires a turing complete language mapping from the input value to output, having access to memory and processing facilities. typically with some operations on the fundamental types included. There are so many ways to structure the same computation.

essentially we want to decompose a problem and compose an answer, logical branching and iteration. 

in jungle a contact has an alternate form, it is as much a caller as it is called. you could have a single call in and then a dozen calls out.

without the constraint of an ordinary function how would you create a language that captured these thoughts

what is implicit in a function 

    source of callers
    sink to call through 
    static stateless (domain bound)
    access to primative funct

<f> :
    |: [[destructure]]
    ! 

4 hierarcical breakdowns

destructure of input value
restructure forward argumnent
destructure forward result
restructure return value


It seems that there are too many trees

each destructuring strategy represents a certain impenetrable form of translation from many to one. like summing or object creation.


destructure of input creates scoped names for things  (like let)
restructure has access to that scope

destructured response adds or overrides those names,
restructure return accesses

what we see is two alternate versions of what the names mean. 

input -> forward -> response -> output
  |         |           |          |
create meaning          |          |
    interpret meaning   |          |
                create more meaning|
                          interpret more meaning 
         
the form of the op is this 4 pointed 
verbosely  

but even then you want to have further injections of names based off translations of some names but that is already done once (during the forwarding)

what if instread of a single forward there was unlimited but each was certainly demarcated. YOu would find that there were a few ways to break down the process
 
1) select from the scope, transform and inject back into the scope under the same(a) or other(b) name  (open scope transform)
2) envelope the current scope transform and produce a new one.  (closed scope 
3) restructure from the current scope and pass to extenal process or forward then destructure into the current scope 

subscope =>  restructure >| transform |< destructure  

transform => [
    open subscope
    closed subscope
    primative transform
]

open subscope  => ( destructure |<  ( subscope )  >| restructure )
closed subscope => ( destructure|<  [ subscope ]  >| restructure )

in such a language a bifacing system is entirely possible, 

destructure and restructure should have a similar syntax and that syntax matches the structural syntax of the jungle-language

--- 

distinction from media, laws and contacts. These functional expressions are in a sense the missing piece, while the media are capable of handling many to many interactions through a space they couldn't handle any data processing. The key similarity that points at some redundancy or double handling is in the destructuring and furthermore in the use of arrows to indicate stages of a process. 

laws designate many and target many, the symbolic bindings mean that these may be identified, individually or as members of a group, with certain tags. Each invocation of message from a source is spread to many places. in a way, the middle expression of a law is a means to perform direective branching. 

here is an example where the message is said to everyone

<~> 
    ! *$sayer -> { message -> `${sayer} says ${message} to ${saidto}` } -> *$saidto 

the directive branching occurs when we consider the scope to have multiple outputs. In the above example no message wouldbe sent through because the default restructure is the return value.

to actually send the message you need something like

{ message -> ( 'message :${message} from ${sayer} >| saidto |<) }

here we leave off the final restructure 

to pass back the response of the target 

{ message |- 
    ( message >| saidto |< response )        
           -| response }

further a symbolic binding is not single, it is automatically distributive, which is where the media tend to have the differences in how to deal with multiple calls and return values to a single scope. 

operators. 
    algebraic + - * / % // 

in a contact there is only one or two outlets. 

@ in  
@ out
  or
@ through

a contact might also have access to a value. 

{ message / value |< elaborations  >| result / reduced }

a contact is also the most convenient place to deal with blocking and non blocking calls, if it is blocking it will not begin a new scope until the last is complete.


