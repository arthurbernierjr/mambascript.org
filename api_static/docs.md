---
title: 'Docs'
subTitle: "Let's Build With"
excerpt: 'This is the MambaScript Page'
featureImage: '/img/Mamba_Script_Logo_Final-05.png'
date: '10/21/21'
---
<center>

#### [Click Here To Go To Start-Here](/start-here)
#### [Click Here To Go To Getting Ready to Learn MambaScript](/learning-mambascript)
#### [Click Here To Go To Docs](/docs)

# What we are doing
```bash
The computer programmer is a creator of universes for which he alone is responsible.
Universes of virtually unlimited complexity can be created in the form of computer programs.
- Joseph Weizenbaum, Computer Power and Human Reason
```

# Computers
Back in the day when personal computers were first hitting the scene you couldn't use one without
some knowledge of how to code.
Nowadays computers are everywhere and most users do not get much further than clicking things with a mouse.
For non-developers this is awesome, could you imagine how bad Apple sales would be if you had to take a college
programming class just to log on to your facebook, even more facebook, ig and the rest wouldn't exist altogether.
For those of us that want to get into that computer and give it commands in code, this means we have to jump through certain hoops.
Enter the terminal, text editors like Atom and other tools like it.

Computers communicate in zeros and ones in what's known as binary. Programs that computers read look something like this :

```bash
00110001 00000000 00000000 00110011 00000001 00000010
00100010 00000010 00001000 01000001 00000001 00000001
01100010 00000000 00000000 00110001 00000001 00000001
01010001 00001011 00000010 01000011 00000001 00000000
00010000 00000010 00000000
```
This is the code that would add the numbers from 1 to 10 together and print it.
This obviously is ridiculous to write and shout out to the old school developers
that had to do this. Writing programs back in the day took alot of tedious
trial and error, and writing some of the complex applications that we use today
were completely inconceivable, could you imagine using those zeros and ones to
create google maps?

The code above could be written out in English line by line like this
```bash
1) Store the number 0 in memory location 0
2) Store the number 1 in memory location 1
3) Store the value of memory location 1 in location 2
4) Subtract the number 11 from the value in location 2
5) If the value in memory location 2 is the number 0, continue with instruction 9
6) Add the value of memory location 1 to location 0
7) Add the number 1 to the value of memory location 1
8) Continue with instruction 3
9) Output the value of memory location 0
```

Now the english above is way more readable but somewhat unpleasant to write out
each task must be written one by one we can improve upon this with the text below.

```bash
Set 'total' to 0
Set 'count' to 1
[loop]
Set 'compare' to 'count'
Subtract 11 from 'compare'
If 'compare' is zero, continue at [end]
Add 'count' to 'total'
Add 1 to 'count'
Continue at [loop]
[end]
Output 'total'
```

This program is very easy to read. The first two lines give two memory locations
total and count. We also initialize the values to `0` and `1` respectfully.
The lines using `compare` are probably the weirdest ones What the program wants
to do is see if count is equal to 11, in order to decide whether it can stop yet.
Because the ma- chine is so primitive, it can only test whether a number is zero,
and make a decision (jump) based on that. So it uses the memory location labelled
compare to compute the value of count - 11, and makes a decision based on that
value. The next two lines add the value of count to the result, and increment count
by one every-time the program has decided that is not 11 yet. Here is the same
program in MambaScript :

```coffee
total = 0
count = 1

while count <= 10
  total += count
  count += 1
present total
```
This program is a definite improvement we are able to write way less lines of
code. The keyword `while` makes things incredibly simple. In our previous code
we had to jump back and forth, but now we no longer have to do that. This can also
be expressed in an even more succinct way in MambaScript.

```coffee
total = 0
total += count forEvery count in [1..10]
present total
```
The following code in MambaScript does in three lines what the other code above
did in many more.

```coffee
total = 0
total += count forEvery count in [1..10]  
present total  
```
Create a position in memory called total and set value to 0, and then `forEvery`
and `in` keywords goes through the range of numbers from 1 to 10, assigning each number to count in turn. Each value in count is then added to total.

We can also use something that we'll see shortly called a function that would allow
us to write everything in one line

```coffee
present sum([1..10])
```

### or

```coffee
present [1..10].sum()
```

# Basic MambaScript

## Values and Variables

Values can have different datatypes and their are 6 basic types in MambaScript

### Numbers
Numbers are written the way numbers are usually written
```coffee
144
```
### Strings
Strings are used for storing and manipulating text. A String in MambaScript is
zero or more characters written inside of quotes.

```coffee
goat = 'Kobe Bryant'
```

You can use either single or double quotes:

```coffee
carName1 = 'Mercedes Benz S550'
carName2 = "Tesla Model S"
```

You can also create multiline strings with either triple single quotes, or triple
double quotes.

```coffee
theRaven = '''
    Once upon a midnight dreary while I pondered, weak and weary,
    Over many quaint and curious volume of forgotten lore -
    While I nodded, nearly napping, suddenly there came a tapping,
    As of some one gently rapping, rapping at my chamber door
    "'Tis some visiter". I muttered, "tapping at my chamber door" -
    "only this and nothing more."

    Ah distinctly I remember it was in the bleak December;
    And each separate dying ember wrought its ghost upon the floor.
    Eagerly I wished the morrow - vainly I had sought to borrow,
    From my books surcease of sorrow - sorrow For the lost Lenore -
    For the rare and radiant maiden whom the angels name Lenore -
    Nameless here For evermore
'''

hamlet = """
    To be or not to be, that is the question
    Whether tis Nobler in the mind to suffer
    The Slings and Arrows of outrageous Fortune,
    Or to take Arms against a Sea of troubles,
    And By opposing end them, to die, to sleep
    No more. and By a sleep, to say we end
    The heart-ache and the thousand Natural shocks
    That Flesh is heir to?
"""
```

### Booleans
A MambaScript Boolean represents one of two types of values: `truthy and falsey`

Truthy values are values that the MambaScript compiler considers `true` and are of
the type Boolean. `yes, on and true`

Falsey values are values that the MambaScript compiler considers `false` and are of
the type Boolean. `no, off and false`

```coffee
present '------- is  and Booleans --------'
present 'Truthy Booleans true, on, yes'
present 'Falsey Booleans false, off, no'
present true is on
present true is yes
present false is off
present false is no
```

### Objects

Objects in MambaScript are a way to store data that in an individual container

```coffee
obj =  {
  "MambaScript":	"JavaScript"
  "is": "==="
  "isnt":	"!=="
  "not":	"!"
  "also":	"&&"
  "or":	"||"
  "true yes on":	"true"
  "false no off":	"false"
  "@ this": 	"this"
  "of": "in"
  "in": "no JS Equivalent"
}
```

### Functions
Functions are one of the fundamental building blocks in MambaScript. A function in MambaScript is similar to a procedure—a set of statements that performs a task or calculates a value, but for a procedure to qualify as a function, it should take some input and return an output where there is some obvious relationship between the input and the output. To use a function, you must define it somewhere in the scope from which you wish to call it.
```coffee
# eat is a function that accepts a string and returns nothing
eat :: String -> () = (food :: String ) ->
  present "yum #{food.toUpperCase()} !!!"

eat food forEvery food in ['toast', 'cheese', 'wine']

eat food forEvery food in  ['toast', 'cheese', 'wine'] when food isnt 'cheese'
```
### Undefined and Null Values
```coffee
a :: Int?
a = 1
a = null

b :: Int = 1
# b = a # can't assign nullable to non-nullable
a = b

listWithNull :: Int?[] = [1, 2, 3, null, 5]
listMaybeNull :: Int?[]? = null
listMaybeNull = listWithNull

intByConditional :: Int =
  if Math.random() > 0.5
    1
  else
    2

# can't be Int
nullableIntByConditional :: Int? =
  if Math.random() > 0.5
    1

intBySwitch :: Int =
  switch ~~(Math.random()* 10)
    when 1
      1
    when 2
      2
    else
      3

# can't be Int
nullableIntBySwitch :: Int? =
  switch ~~(Math.random()* 10)
    when 1
      1
    when 2
      2
```

## Control Flow
Coming Soon

## What is a pessimistic type interface?

To pass the dynamic type system, MambaScript expects symbol to be `implicit` node by default. If compiler compares implicit node type and implicit node type fails, it recovers to `implicit` `Any` automatically.

## Examples

### Assigment with type

```coffee
n :: Int = 3
```

### Pre defined symbol

```coffee
x :: Number
x = 3.14
```

### Nullable

```coffee
x :: Number?
x = 3.14
x = null
```

### Typed Array

```coffee
list :: Int[] = [1..10]
listWithNull :: Int?[] = [1, null, 3]
```

In `v0.10`, imperfect to struct.

### Struct

```coffee
struct Point
  @name :: String
  x :: Number
  y :: Number
p :: Point = {x: 3, y: 3}
name :: String = Point.name

struct Point3d implements Point
  z :: Number
```

### Module

MambaScript has module system like TypeScript

```coffee
module A.B
	class @C
		a :: Int
abc :: A.B.C = new A.B.C
```

### Typed Function

```coffee
# pre define
f1 :: Int -> Int
f1 = (n) -> n

# annotation
f2 :: Number -> Point = (n) -> x: n, y: n * 2

# multi arguments
f3 :: (Int, Int) -> Int = (m, n) -> m * n

# another form of arguments
f4 :: Int * Int -> Int = (m, n) -> m * n

# partial applying
fc :: Int -> Int -> Int
fc = (m) -> (n) -> m * n
```

### Blueprint instead of class with this scope

```coffee
blueprint X
  # bound to this
  num :: Number
  f   :: Number -> Number

  f: (n) ->
    @num = n

x :: X = new X
n :: Number = x.f 3
```

### Blueprint with implements

```coffee
blueprint Point
  x :: Int
  y :: Int

struct Size
  width  :: Int
  height :: Int

blueprint Entity inheritsFrom Point implements Size
e :: {x :: Int, width :: Int} = new Entity
```

### Generics and type arguments

```coffee
# struct
struct Value<T, U>
	value :: U
struct Id<A, B>
	id :: Value<A, B>
obj :: Id<Int, String> =
  id:
    value: 'value'

# function type arguments
map<T, U> :: T[] * (T -> U) -> U[]
map = (list, fn) ->
  for i in list
    fn(i)
list :: String[] = map<Int, String> [1..10], (n) -> 'i'

# blueprint type arguments
blueprint Blueprint<A>
  f :: Int -> Int
  constructor :: A -> ()
  constructor: (a) ->
c = new Blueprint<Int>(1)
```

# [Click Here To Go To Start-Here](/start-here)
# [Click Here To Go To Getting Ready to Learn MambaScript](/learning-mambascript)
# [Click Here To Go To Docs](/docs)

</center>
<small> Inspired By 'Smooth CoffeeScript', 'You Don't Know JS', and 'Eloquent JavaScript' </small>
