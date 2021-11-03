---
title: 'Quick Look In MambaScript'
subTitle: 'A quick look at some features in MambaScript'
excerpt: 'I want to be the best. I want to be the best simple and plain, thats what drives me - Kobe Bryant'
featureImage: '/img/mamba.gif'
date: '10/28/21'
---

## Getting Started

Install and run!

```bash
$ npm install -g mambascript
$ mamba -c foo.mamba # compile
$ mamba foo.mamba # execute
$ mamba # repl
$ start-mambascript #start a new mambascript project
```

### Extensions you should know about MambaScript

- `.mamba` are compiled by mambascript compiler.

<hr/>

```coffee
	# Concatenate string
	present '-------Concatenate string--------'
	present 'Concatenate -->',  'con' + 'cat' + 'en' + 'ate'

	# typeof operator
	present '-------TYPEOF operator--------'
	present 'Typeof Operator -->', typeof 'arthur'

	# isnt
	present '-------ISNT instead of !== --------'
	present 'ISNT -->' , 'Love' isnt 'Hate'

	# and , && , also
	present '------- also --------'
	present 'ALSO -->', 5 > 3 also 6 > 5

	# or, ||
	present '------- or --------'
	present 'OR -->', true or false

	# not
	present '-------NOT--------'
	present not true

	# is  and Booleans
	present '------- is  and Booleans --------'
	present 'Truthy Booleans true, on, yes'
	present 'Falsey Booleans false, off, no'
	present true is on
	present true is yes
	present false is off
	present false is no


	# Types

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

	keys :: String[] = Object.keys obj

	forEvery key in keys then present "[#{key}] in MambaScript is equivalent to [#{obj[key]}] in JavaScript" unless key is 'MambaScript'

	# Strings

	myString :: String = 'arthur'

	present myString.split('').reverse().join('')
	present typeof myString

	# Numbers

	myNumber :: Number = 5

	present 'myNumber is', myNumber
	present myNumber * 2
	present myNumber ** 2
	present myNumber % 3
	present myNumber / 2


	# Booleans
	myBoolean :: Boolean = yes
	present 'myBoolean is', myBoolean

	# Objects
	myObj =
		name: 'arthur'
		age: 32
		lights: on
		hair: true

	present myObj
	# Arrays
	numArr :: Int[] = [1,2,3]
	stringArr :: String[] = ['a', 'b', 'c']
	otherArr :: Any[] = [1, 'a']
	present otherArr

	# Loops & Control Flow

	forEvery number in [0..12] by 2 then present number

	forEvery number in [0..10]
		do (number) ->
			present number * 3

	# eat is a function that accepts a string and returns nothing
	eat :: String -> () = (food :: String ) ->
		present "yum #{food.toUpperCase()} !!!"

	eat food forEvery food in ['toast', 'cheese', 'wine']

	eat food forEvery food in  ['toast', 'cheese', 'wine'] when food isnt 'cheese'
	# Blueprints

	blueprint Human
		name :: String
		age :: Int
		constructor: (age :: Int, name :: String) ->
			@name = name
			@age = age

	blueprint SuperHero inheritsFrom Human
		name :: String
		age :: Int
		powers :: String[]

		constructor: (name :: String, age :: Int, powers...) ->
			super name, age
			@powers = powers

	bigArt = new SuperHero 'Big Art', 33, 'flight', 'super strength'

	present bigArt

	# Functions

	# Structs

	# Generics

```

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

TypedCoffeeScript has module system like TypeScript

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
