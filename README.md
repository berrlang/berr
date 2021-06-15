# berr
Welcome to the berr programming language.  
Programming language that you type sentences ?

Syntax is kind of simillar to python and possibly javascript

### To Do
- [x] Come up with a name
- [ ] Finalize the syntax
- [x] Figure out what programming language to write the compiler/interpreter in
- [x] Figure out if the lang is compiled or interpreted or both
- [ ] Low or high level

I plan to write berr in [scrap](https://github.com/scrap-lang/scrap)  
berr will be both compiled and interpreted but the compiler will be made first.

### Whats so nice about this?
I dont know yet but here is what I can try to follow
- Words and commas ? 
- Readable code. Almost like it isnt even code..
- Types or no types? idk
- Everything is confusing right now: yes
- You want to help? Hopefully you have knowledge on making programming langs. Ill give you a secret _join my dev discord server_ <- Im useless and didnt put a link so you can find it on my profile (btw Im insberr) 

## Idea
The idea is that it's all typed out like you are talking, or, more like writing.  
Truly going to be hard to make a language like this, but it's worth a try.


I want to avoid the use of : ; ( ) { } as much as possible


TODO
- Syntax for what functions return
- Syntax for the end of statements (. probably)
- other crazy ideas for things I wish were built into programming languages


#### Types
```br
string

int
float
number

hex
byte

array
json
bdm
// maybe some others like yaml

any
none
empty
void

enum
struct
class
```

#### Symbols
```br
=
==
!=
?
??
&&
||
!!
<
<=
>
>=
>
^
/
*
%
+
-
+:

+=
/=
-=
*=

++
--
**
// // looks like a comment.. but its not. hmmm

\regex\g

{ name: "insberr", { what: "nothing" } }
{ hi: (a, b, c) { print "hello world. and hello @in.name " + a + b + c }, name: "insberr" }

0123456789

$debug, print "debugging"
```


#### Strings

This will print a string
```br
print "This is a string"
```

Combineing strings
```br
name ins be "Hello " + "World!"
```

Hate adding the space? Add a `:` after the `+` to make it do it for you
```br
name berr be "Hello" +: "World!"
```
`"Hello World"`

And to add more than one space add the number of spaces you want after the `:`
```br
name berr be "Hello" +:3 "World!"
```
`"Hello   World"`


Increment strings
```br
name planet be "mars "
planet++
```
`planet` = `"mars mars"`

Increment more than once by adding `:n` after the `++`
```br
name planet be "mars"
planet++:5
```
`planet` = `"mars mars mars mars mars mars"`

Increment a `n` amount of times from the value of a variable
```br
name x be 2
name planet be "mars "
planet++:x
```
`planet` = `"mars mars mars"`


#### Variables

Declare a variable with the `name` keyword
```br
name ins
```

Declare a variable with an inital value using `be` or `=`
The `be` keyword is preferred over `=` and `be` will be used for the rest of the syntax ideas
```br
name ins be 3
name berr = 4
```

You cannot declare a variable under the same name more than once as it will cause an error
```br
name ins be 4
name ins be 7
```
`compile time error: cannot declare 'ins' twice`

You can set the variable value type and that variable can only ever be that type
```br
name ins type int
// or with an inital value
name berr be 4 type int
```

To change the value of a variable use `set`
```br
name ins be 6

set ins to 5
```

`set` is not required but makes it easier to see whats happening
```br
ins to 9
```


------
```br
// keywords like 'to' and 'be' can be replaced with an '=' if you prefer that
name ins = 6
set ins = 9
// same as
name ins be 6
set ins to 9


// variables are muteable by default
// you can put unm
name unm berr be 5
// attempting to change the value of 'berr' will throw an error
set berr to 7 // error

```

#### Functions

Im still deciding on the "what the function returns" syntax
so it is a bit confusing

functions are global in their scope.
function definition placement does not matter
this means

```br
print run hello("world").
make hello with (input), return "hello @input"
```
and
```br
make hello with (input), return "hello @input"
print run hello("world")
```
will print "hello world"


Use the `make` keyword to create a function
```br
make my_function,
{
  print "Hello world"
}
```

```br
make my_function,
print "Hello World" // period can go here
. // or here
```

```br
/*
a wordy description of whats happening
'make' a function named 'myFunction' 'with' the parameters '(name, age, city)' 'that' 'returns' '1' 'value',
  in this function 'return' 1 value, '"Hello @name, you are @age, you live in @city"'
*/


// here is where things get a bit complex
// a function does not have to have its operations indented
// however if you do not indent make sure there is a 'return' or 'end' statement
make hello with (input),
print "hello @input"
end

// you can also use curly braces (indent not required)
make hello with (input) {
  print "hello @input"
}





// one line code, useful for minifying code
// simple, just add a '.' to the end

// one line functions do not need a 'return' or 'end' but do require a '.'
name ins be "ins". print "hello berr". make world with (a), print "a".


```



**old examples**  

Only an idea but here is an example:

```br
declare x and set it to 1
if x is 0, then
  print "Hello World"
otherwise,
  set x to 0
```

The above example is only an idea. Of course no one wants to write a long statement to set a variable named x to 1, but the idea is there.

Here are a few other ideas:

```br
// Idea 1

make x, set to 1

if x is 0,
  print "Hello World"
otherwise
  set x to 0


// Idea 2

// Declaring a new variable and setting it to 
make x be 1

if x is 0 then,
  print "Hello World"
otherwise,
  set x to 0


// more ideas

make arr be ["red", "orange", "yellow"]

for every color in arr, print the color

// would print:
// red
// orange
// yellow




wait 10 seconds, then print "Waited 10 seconds"



// functions
// make for function declaration and name for variables?

make testFunction with (?a is 1, !b, ?c) that returns 1 value,
  print a b and c
  return add a, b, and ?c

name a and run testFunction where,
  b is 2
  c is 1

print a

// 4



// variable that's value can be changed
name meaning_of_life be 1

// variable that's value can't be changed
name meaning_of_life is 1


// changing the value of a variable
name meaning_of_life be 1
set meaning_of_life to 42



// More wordy idea

// Indentation is not required but makes it easier to read
make a function named sum with (a as a number, b as a number, c as a number or no value) that returns a number,

  name x with a value of 0

  set x to a plus b plus ?c
  return x

// there must be a return or end statement at the end of a function

print the output of sum(10, 20)     // 30
print the output of sum(10, 20, 30) // 60
print sum(10, 20)                   // sum(10,20) => 30

```

```
declare age as number.

ask "How old are you?" -> set age to it.
ask "How old are you?" -(input)> set age to input.

set age to output of ask "How old are you?".
set age to (ask "How old are you?").

if age is 0
```

Of course this is all just an idea. I don't even know how to make a programming language so this might stay an idea.





