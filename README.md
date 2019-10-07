# Optionals lab

Fork and clone this repo. On your fork, answer and commit the follow questions. When you are finished, submit the link to your repo on Canvas.


## Question 1

a. Given the variable `userNameOne` below, print *"The username is Test User"*.  Use *Optional Binding* (`if let`) to print the name.

```swift
var userNameOne: String? = "Test User"
```
# Answer
```swift
var userNameOne: String? = "Test User"

if let userName = userNameOne {
    print("The username is \(userName)")
}
```
b. Given the variable `userNameTwo` below, print *"The username is undefined"*.  Use the *nil coalescing operator* (`??`).

```swift
var userNameTwo: String? = nil
```
# Answer
```swift
var userNameTwo: String? = nil
let username = userNameTwo ?? "The username is undefined"

print(username)
```

## Question 2

a. Given the variables `rectOneWidth` and `rectOneHeight` below, print "The area of rectOne is 50".  Use *Optional Binding* (`if let`) to print the area.

```swift
var rectOneWidth: Double? = 5
var rectOneHeight: Double? = 10
```
# Answer
```swift
var rectOneWidth: Double? = 5
var rectOneHeight: Double? = 10

if let oneWidth = rectOneWidth , let oneHeight = rectOneHeight {
    let rectArea = oneWidth * oneHeight
    print(rectArea)
    print("The area of rectOne is \(Int(rectArea))")
}
```

b. Given the variables `rectTwoWidth` and `rectTwoHeight` below, print "The are of rectTwo is not able to be calculated".  Use *Optional Binding* (`if let`) to print this message.

# Answer

```swift
var rectTwoWidth: Double? = nil
var rectTwoHeight: Double? = nil

if rectTwoWidth != nil && rectTwoHeight != nil {
    let area = rectTwoWidth! * rectTwoHeight!
    print(area)
} else {
    print("The area of rectTwo is not able to be calculated")
}
```

## Question 3

a. Given the variables `userOneName`, `userOneAge`, and `userOneHeight` below, write code that prints "Hello Anne!  You are 15 years old and 5.8 feet tall" (1 foot = 12 inches).  Use optional binding.

# Answer
```swift
var userOneName: String? = "Anne"
var userOneAge: Int? = 15
var userOneHeight: Double? = 70

if let height = userOneHeight , let name = userOneName , let age = userOneAge {
    let feet = height / 12.0
    print("Hello \(name)! You are \(age) years old and \(Float(feet)) tall")
}
```


b. Given the variables `userTwoName`, `userTwoAge` and `userTwoHeight` below, write code that prints "Hello user!  You are 15 years old and I don't know how tall you are".  Use optional binding

# Answer
```swift
var userTwoName: String? = nil
var userTwoAge: Int? = 15
var userTwoHeight: Double? = nil

if let age = userTwoAge {
    if userTwoName == nil && userTwoHeight == nil {
        let name = "user"
        let height = "I don't know how tall you are"
        print("Hello \(name)! You are \(age) years old and \(height)")
    }
}
```


## Question 4

Give the variable `favoriteNumber`, write code that either prints "Your favorite number is " followed by the number, or "I don't know what your favorite number is"

`favoriteNumber` is of type Int? and will either be `nil` or a random number between 0 and 10.  It will change each time you run your Playground.

# Answer
```swift
var favoriteNumber = Bool.random() ? Int.random(in: 0...10) : nil

if favoriteNumber == nil {
    print("I don't know what your favorite number is")
} else {
    print("Your favorite number is \(favoriteNumber!)")
}
```



## Question 5

Given the variables `numOne`, `numTwo` and `numThree`, write code that prints "The sum of all the numbers is " followed by their sum.  If a number is `nil`, don't add it to the sum.  If all numbers are `nil`, the sum is zero.

# Answer
```swift
var numOne = Bool.random() ? Int.random(in: 0...10) : nil
var numTwo = Bool.random() ? Int.random(in: 0...10) : nil
var numThree = Bool.random() ? Int.random(in: 0...10) : nil

if numOne == nil {
    numOne = 0
}
if numTwo == nil {
    numTwo = 0
}
if numThree == nil {
    numThree = 0
}
if numOne == nil && numTwo == nil && numThree == nil {
    print("The sum is 0")
} else {
    print("The sum of all the numbers is \(numOne! + numTwo! + numThree!)")
}
```

## Question 6

a. Given the variable `numbers` below, write code that prints "The sum of all the numbers is " followed by their sum.  If a number is `nil`, don't add it to the sum.  If all numbers are `nil`, the sum is zero.

# Answer

```swift
var numbers = [Int?]()

for _ in 0..<10 {
    numbers.append(Bool.random() ? Int.random(in: 0...100) : nil)
}
print()
print(numbers)
var noNilSum = 0
var numCount = 0

for currentNum in numbers {
    // optional binding
    if let validNum = currentNum { // optional binding to unwrap the current num
        noNilSum += validNum
        numCount += 1
    }
}
let noNilAvg = noNilSum / numCount
print(noNilSum)
print(noNilAvg)
```

b. Using the same variable, find the average of all non-nil values.
# Answer
## is in part a

## Extra Questions

https://github.com/joinpursuit/Pursuit-Core-iOS-Extra-Optionals-Questions/blob/master/README.md
