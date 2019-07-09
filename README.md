# Optionals lab

Fork and clone this repo. On your fork, answer and commit the follow questions. When you are finished, submit the link to your repo on Canvas.


## Question 1

`var userName: String?`

Write 3 different ways of safely unwrapping and printing the value of `userName`.  If it is nil, print "No name".

- Method one: Check for nil and force unwrap

- Method two: Optional binding

- Method three: Nil coalescing

var userName: String?

//Method 1

if userName == nil {
print("No name.")
} else {
print(userName!)
}

//Method 2

if let name = userName {
print(name)
} else {
print("No name.")
}

//Method 3

var name = userName ?? "No name."

print(name)


## Question 2

Given optional string `backgroundColor`, write code that safely unwraps and prints it. If backgroundColor is nil, give it a value.

`var backgroundColor: String?`

var backgroundColor: String?

var color = backgroundColor ?? "blue"

print(color)

## Question 3

Given an optional width and an optional height of a rectangle, write code that calculates and prints the area. Print an error message if either value is nil.

```swift
var width: Double?
var height: Double?


var width: Double? = 5.0
var height: Double? = 5.0

if let h = height, let w = width {
print("Area is",h * w)
} else {
print("One or both values aren't defined.")
}

```


## Question 4

Given the following optional variables `name`, `age` and `height`. Write code so that it prints `name`, `age` and `height` if they all have a value. If any are nil, print an error message. Try using optional binding.

```swift
var name: String?
var age: Int?
var height: Double?

var name: String? = "Joe"
var age: Int? = 38
var height: Double? = 5.7

if let userName = name, let userAge = age, let userHeight = height {
print("Name:",userName)
print("Age:",userAge)
print("Height:", userHeight)
} else {
print("One or more values aren't defined.")
}

```


## Question 5

Given the variables `firstName`, `middleName` and `lastName`. Create a variable called `fullName` that is a nicely formatted string.

```swift
var firstName: String = "Johnny"
var middleName: String?
var lastName: String = "Stone"

var firstName: String = "Johnny"
var middleName: String? 
var lastName: String = "Stone"

if let middle = middleName {
let fullName = "\(firstName) " + "\(middle) " + "\(lastName)"
print(fullName)
} else {
let fullName = "\(firstName) " + "\(lastName)"
print(fullName)
}

```


## Question 6

Write code that adds 15 to `myIntString`, then prints the sum. Use the `Int()` constructor which returns an optional Int `(Int?)`.

`let myIntString = "35"`

let myIntString = "35"
var string: String? = myIntString


if let unwrappedString = string {
if let unwrappedInt = Int(unwrappedString) {
print(unwrappedInt + 15)
}
}

## Question 7

Given an optional tuple of optional Ints, write code to safely unwrap the tuple and calculate the sum of its contents that aren't nil.

```swift
var scores: (Int?, Int?, Int?)?

var testCaseOne = (4, nil, 7)
var testCaseTwo = (nil, nil, 9)
var testCaseThree = (5, 10, 24)





```


## Question 8

Safely unwrap `tuple` if there’s a non-nil tuple value and print it out.

```swift
var tuple: (Int, Int)?
if Bool.random() {
 tuple = (5, 3)
}

var tuple: (Int, Int)?
if Bool.random() {
tuple = (5, 3)
}

if let tupleValue = tuple {
print(tuple!)
} else {
print("nil")
}

```


## Question 9

Write code that either doubles `myInt` and then prints it, or prints an error message if myInt is nil.

```swift
let myInt: Int?
if Bool.random() {
 myInt = 5
}


var myInt: Int?
if Bool.random() {
myInt = 5
}

if let int = myInt {
print(int * 2)
} else {
print("Error: Undefined.")
}

```


## Question 10

Write code that prints out the product of `myDouble` and `doubleTwo` or prints an error message if `myDouble` is nil.

```swift
var myDouble: Double?
let doubleTwo: Double = 5

if Bool.random() {
 myDouble = 12
}

var myDouble: Double?
let doubleTwo: Double = 5

if Bool.random() {
myDouble = 12
}

if let doubleOne = myDouble {
print(doubleOne * doubleTwo)
} else {
print("Error: Undefined")
}

```


## Question 11

Determine if the variable contains a Boolean or nil value. If nil set the variable to false, else keep it true.

```swift
var isTheGreatest: Bool?

if Bool.random() {
 isTheGreatest = true
}

var isItReallyTheGreatest = isTheGreatest ?? false

print(isItReallyTheGreatest)

```


## Question 12

Given the code below print the sum of each non-nil element in `myTuple`.

 ```swift
var myTuple: (Int?, Int?, Int?, Int?)

if Bool.random() {
 myTuple.0 = 5
 myTuple.2 = 14
} else {
 myTuple.1 = 9
 myTuple.3 = 10
}

if let tuple0 = myTuple.0, let tuple2 = myTuple.2 {
print(tuple0 + tuple2)
} else {
if let tuple1 = myTuple.1, let tuple3 = myTuple.3 {
print(tuple1 + tuple3)
}
}

```


## Question 13

Given the helper functions and code below, check to see if your `evolutionaryStone` is able to evolve your pokemon.  The table below shows the appropriate matches of pokemon to stone:

| Pokemon	   | Stone    |
| :--------: | :------: |
| Pikachu	   | Electric |
| Bulbasaur	 | Grass    |
| Charmander | Fire     |
| Squirtle	 | Water    |


```swift
// Helper Functions

func eStone() -> String {
 let random = Int(arc4random_uniform(5))
 switch random {
 case 0:
  return "Electric"
 case 1:
  return "Grass"
 case 2:
  return "Fire"
 case 3:
  return "Water"
 default:
  return "No Stone"
 }
}

func starterPokemon() -> String {
 let random = Int(arc4random_uniform(5))
 switch random {
 case 0:
  return "Pikachu"
 case 1:
  return "Bulbasaur"
 case 2:
  return "Charmander"
 case 3:
  return "Squirtle"
 default:
  return "Not a Pokemon"
 }
}

let pokemon: String?
var evolutionaryStone: String?
pokemon = starterPokemon()
evolutionaryStone = eStone()




if let check = pokemon {
if let check2 = evolutionaryStone {
if check == "Pikachu" && check2 == "Electric" {
print("Pikachu is evolving!")
} else if check == "Pikachu" && check2 != "Electric" {
print("Pikachu can't evolve.")
}
if check == "Bulbasaur" && check2 == "Grass" {
print("Bulbasaur is evolving!")
} else if check == "Bulbasaur" && check2 != "Grass" {
print("Bulbasaur can't evolve.")
}
if check == "Squirtle" && check2 == "Water" {
print("Squirtle is evolving!")
} else if check == "Squirtle" && check2 != "Water" {
print("Squirtle can't evolve.")
}
if check == "Charmander" && check2 == "Fire" {
print("Charmander is evolving!")
} else if check == "Charmander" && check2 != "Fire" {
print("Charmander can't evolve.")
}
}
}
```


## Question 14

Given an optional int `numberOfPeople`, write code that unwraps and prints it **only if it is even**. Try using optional binding with a condition.

```swift
var numberOfPeople: Int?

if Bool.random() {
 numberOfPeople = 108
}

var numberOfPeople: Int?

if Bool.random() {
numberOfPeople = 108
}

if let people = numberOfPeople {
if people % 2 == 0 {
print(people)
}
} else {
print("No people.")
}

```


## Question 15

Given the array of optional Ints `someNumbers`, write code to find the product of the array not including any nil values.

```swift
var someNumbers: [Int?] = []

for i in 0..<20 {
    someNumbers.append(Bool.random() ? i : nil)
}

var product = 1


for i in someNumbers {
if i != nil {
product *= i!
} else {
continue
}
}

print(product)
```


## Question 16

Given the array `poorlyFormattedCityNames`, create a new array with the city names capitalized and any nil values removed.

```swift
let poorlyFormattedCityNames: [String?] = ["new york", "BOSTON", nil, "chicago", nil, "los angeles", nil, "Dallas",]

Output: ["New York", "Boston", "Chicago", "Los Angeles", "Dallas"]


var properCityNames: [String] = []


for i in poorlyFormattedCityNames {
if i == nil {
continue
}
properCityNames += [i!.capitalized]
}

print(properCityNames)
```


## Question 17

Given a random array of optional numbers, create a new array of all the even numbers that aren't nil.

```swift
var aBunchOfNumbers: [Int?] = []

for _ in 0..<20 {
 aBunchOfNumbers.append(Bool.random() ? Int(arc4random_uniform(102)) : nil)
}

var aBunchOfEvenNumbers: [Int] = []

for i in aBunchOfNumbers {
if i == nil {
continue
}
if i! % 2 == 0 {
aBunchOfEvenNumbers += [i!]
} else {
continue
}
}

print(aBunchOfEvenNumbers)

```


## Question 18

Given the following array of zip codes as strings, write code that turns them into an array of Ints.

`let zipCodeStrings = ["11377", "11101", "11373", "10014", "10003", "11223"]`

var IntArray = zipCodeStrings.map { Int($0)! }

print(IntArray)

## Question 19

Some students were asked some questions about their favorite foods and colors and the answers were stored in an array `studentInfo`.

- Print the names of the students that do not have a favorite color.

- Print the names of the students that don't have a favorite color or a favorite food.

- Create a new array of type `[(String, String, String)]` that contains the students with both favorite colors and foods.

`let studentInfo: [(String, String?, String?)] = [("Bill", "Burgers", "Blue"), ("Rita", nil, "Red"), ("Peter", "Pizza", "Purple"), ("Sarah", "Sandwiches", nil), ("Jeff", nil, nil), ("Lucy", "Leftovers", "Lilac"), ("Mike", "Meat", "Mauve"), ("Gemma", nil, "Green")]`


var coolStudents: [(String, String, String)] = []

for info in studentInfo {
if info.1 == nil && info.2 == nil {
print("\(info.0) does not have a favorite food or color.")
continue
}
if info.1 == nil {
print("\(info.0) does not have a favorite food.")
continue
}
if info.2 == nil {
print("\(info.0) does not have a favorite color.")
}
if info.1 != nil && info.2 != nil {
coolStudents.append((info.0, info.1!, info.2!))
}
}

print(coolStudents)

## Question 20

Given an optional array of optional tuples of optional UInt8s,

- Write code to safely unwrap and print the tuples in the array with all 3 RGB values.

- Write code that counts all the nil values.

`let possibleColors: [(r: UInt8?, g: UInt8?, b: UInt8?)?]? = [(128, 21, 7), (0, 0, 0), nil, (nil, 25, 82), (255, 255, 255), nil, (200, 100, nil), (120, nil, 23), (0, 255, 106), (nil, nil, nil), nil, (100, 100, 200)]`


var r: UInt8 = 0
var g: UInt8 = 0
var b: UInt8 = 0
var nilCount = 0

for i in possibleColors! {
if i == nil {
nilCount += 1
}
if let tuple = i {
if let element = tuple.r {
r = element
} else {
nilCount += 1
}
if let element = tuple.g {
g = element
}else {
nilCount += 1
}
if let element = tuple.b {
b = element
}else {
nilCount += 1
}
print("R: " + "\(r) " + "G: " + "\(g) " + "B: " + "\(b) ")
}
}

print(nilCount)

## Question 21

Consider the following nested optional. It corresponds to a number inside a box inside a box inside a box.

- Fully force unwrap and print number.

- Optionally bind and print number.

`let number: Int??? = 10`

let number: Int??? = 10

var boxCutter = number!!!
print(boxCutter)


if let i = number {
if let j = i {
if let unwrapped = j {
print(unwrapped)
}
}
}


## Question 22

Given an Array of Optional Strings, write code that concatenates all non-nil values together except for strings with 3 or more vowels.

`let monkeyingAround = ["orangutan", "apes",nil, "monkeys", "gorillas", "lemurs", nil]`

output: `"apesmonkeyslemurs"`


## Question 23

Given the value below, print out all of the non-nil Ints it contains by accessing each of them.

`var strangeStructure: ([Int]?, [[Int?]], [[Int]?], Int)? = ([1], [[2,3,4],[],[5,nil],[nil]], [nil, [6,7,8],nil,[],[9]], 10)`
