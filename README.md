# KOTLIN BASICS

## Kotlin Background Information
The Kotlin language has been around since 2011, but its popularity took off in 2017 when Google announced Kotlin’s inclusion as a ﬁrst-class language for Android development. In 2019, Google announced a "Kotlin-ﬁrst" approach to Android development.

## Basic Syntax

<details>
<summary>Data types</summary>
Integer: `int` indicates a whole number.

Float: `float` indicates a number with a decimal point.

Double: `double` indicates a number with a decimal point.

Character: `char` indicates a single character.

Boolean: `boolean` indicates a true or false value.

String: `String` indicates a sequence of characters.

`\n` is used to indicate a new line.
</details>

<details>
<summary>Variables</summary>
Variables is a named memory location in kotlin a variable is declared using the `var` keyword or `val`.

```kotlin
var variableName: dataType = value
```

```kotlin
var num: Int = 1
```
Declared a variable called `num` with a value of `1`.
Using it in code:

```kotlin
println(num)
```
You can also declare variables with the val keyword. The difference is that the value of a variable can't be changed.

```kotlin
val num: Int = 1
```
If a variable must be changeable than declare it with the var keyword. Otherwise declare it with the val keyword.

**Type inference**

Kotlin will automatically infer the type of a variable.

```kotlin
var num = 1
```
</details>


<details>
<summary>Operators</summary>
Operators are used to perform actions on variables.

```kotlin
num = num + 1
```
**Assignment operator:**

 `=`

```kotlin
num = num + 1
```
**arithmentic operators:**

 `+`, `-`, `*`, `/`, `%`.

```kotlin
num += 1
```
**increment and decrement operators:** 

`++`, `--`.

**Comparison operators**
```kotlin
num == 1
```
Kotlin also supports comparison operators also called boolean operator: `==`, `!=`, `<`, `<=`, `>`, `>=`.

**Logical operators**

`&&`, `||`

</details>

<details>
<summary>Comments</summary>
Comments are used to explain code.

```kotlin
// This is a comment
```

This is also a comment.

```kotlin
/*
This is also a comment
*/
```
</details>

<details>
<summary>Input</summary>
Input is used to get user input. The `readLine()` function block any action until input is given by the user

```kotlin
var input = readLine()
```
Returns the input as a string to convert to an integer:

```kotlin
var input = readLine()?.toInt()
```
</details>

<details>
<summary>Control flow</summary>

**if expression**

Is a control condition that only allows the action to be performed if the condition is true. Executes once
```kotlin
 if (2 > 1) {
   println("Yes, 2 is greater than 1.")
 } 
```

**If-else**

This is an extended `if-expression` that provides a code which should be run when the expression is false. Exceutes twice

```kotlin
val animal = "Fox"
if (animal == "Cat" || animal == "Dog") {
  println("Animal is a house pet.")
} else {
println("Animal is not a house pet.")
}


val a = 5
val b = 10
val min = if (a < b) a else b
val max = if (a > b) a else b
```

**else-if condition**

Executes more that twice

```kotlin
val hourOfDay = 12
val timeOfDay = if (hourOfDay < 6) {
"Early morning"
} else if (hourOfDay < 12) {
"Morning"
} else if (hourOfDay < 17) {
"Afternoon"
} else if (hourOfDay < 20) {
"Evening"
} else if (hourOfDay < 24) {
"Late evening"
} else {
"INVALID HOUR!"
}
println(timeOfDay)
```

>>Note: If we have only one line of code we can omit the curly braces`{}`

**When expression**
When expression execute a code depending on the constant or variable
```kotlin
val number = 10
when (number) {
 0 -> println("Zero")
 1 -> println("One")
 else -> println("Non-zero")
}

val string = "Dog"
when (string) {
"Cat", "Dog" -> println("Animal is a house pet.")
else -> println("Animal is not a house pet.")
}

val numberName = when (number) {
2 -> "two"
4 -> "four"
6 -> "six"
8 -> "eight"
10 -> "ten"
else -> {
println("Unknown number")
"Unknown"
}
}
println(numberName)

// advance when expression
val hourOfDay = 12
val timeOfDay: String
timeOfDay = when (hourOfDay) {
0, 1, 2, 3, 4, 5 -> "Early morning"
6, 7, 8, 9, 10, 11 -> "Morning"
12, 13, 14, 15, 16 -> "Afternoon"
17, 18, 19 -> "Evening"
20, 21, 22, 23 -> "Late evening"
else -> "INVALID HOUR!"
}
println(timeOfDay)


// when expression with ranges
timeOfDay = when (hourOfDay) {
in 0..5 -> "Early morning"
in 6..11 -> "Morning"
in 12..16 -> "Afternoon"
in 17..19 -> "Evening"
in 20..23 -> "Late evening"
else -> "INVALID HOUR!"
}
```
</details>


<details>
<summary>Loops</summary>

**while loop**

A while loop repeats a block of code while a condition
is true..

```kotlin
var sum = 1
while (sum < 1000) {
sum = sum + (sum + 1)
print(sum)
}
```
*Output:* 1 3 7 15 31 63 127 255 511

**do-while**

In do-while condition is evaluated at the end of the loop rather than at the beginning.

```kotlin
sum = 1
do {
sum = sum + (sum + 1)
} while (sum < 1000)
```

**for-loop**

A for-loop is used to run a code for a certain number of time

```kotlin
 val count = 10
 var sum = 0
 for (i in 1..count) {
   sum += i
 }
```

 **Repeat-loop**

 Repeat-loop gives the capability of repeating the loop for a given time

 ```kotlin
     sum = 1
     var lastSum = 0
     repeat(10) {
     val temp = sum
     sum += lastSum
      lastSum = temp
    }
 ```

  **Steps in loops**
  
  The code below jumps two steps then execute the sum.
  ```kotlin
     var sum = 0
     for (i in 1..9 step 2) {
      sum = sum+i
    }
  ```

  You can even count down in a for loop using downTo.
  ```kotlin
    for (i in 30 downTo 1 step 2) {
        print(i)
    }
  ```

  **forEach-loop**

  ```kotlin
   val nums = arrayOf(1, 2, 3, 4, 5,6,7,8,9,10)
    nums.forEach { num ->
        if(num%2 ==0){
            print(num)
        }
    }
  ```

</details>

<details>
<summary>Break and Continue</summary>
Break is used to exit a loop. Continue is used to skip the current iteration of a loop.

```kotlin
var num = 1
while (num <= 10) {
    if (num == 5) {
        break
    }
    println(num)
    num++
}
```
*Output:* 1 2 3 4
</details>

<details>
<summary>Ranges</summary>
Kotlin allows you to easily create ranges of values using the following syntax:

```kotlin
for (i in 1..10) {
    println(i)
}
```
You can also create ranges of characters:

```kotlin
for (c in 'a'..'z') {
    println(c)
}
```

You can check if a number is present in a value using in:

```kotlin
var num = 5
if (num in 1..10) {
    println("num is in the range")
}
```

To iterate a number which does not include it's end element, use until:

```kotlin
for (i in 1 until 10) {
    println(i)
}
```
</details>

<details>
<summary>Arrays </summary>
An array is an ordered collection of values of the same type with the elements `zero-indexed`
An array is declared with the `arrayOf` function.

```kotlin
var nums = arrayOf(1, 2, 3, 4, 5)
```
To output the second element in the array:

```kotlin 
println(nums[1])
```
You can also change the value of an element in the array:

```kotlin
nums[1] = 10
```
**Array of primitive type**

```kotlin
    val oddNumbers = intArrayOf(1, 3, 5, 7)
```
The various functions to create a primitive array
`IntArray()` ,`DoubleArray()` , `FloatArray()` etc.

```kotlin
    val zeros = DoubleArray(4) // 0.0, 0.0, 0.0, 0.0
    val arr = IntArray(3) { 22 } // 22, 22, 22
```

**Converting Array**

```kotlin
  val otherOddNumbers = arrayOf(1, 3, 5, 7).toIntArray()
```

>>Note: We can iterate over array using the for-loop or forEach loop. 
</details>


<details>
<summary>List</summary>
a list is a similar type to array conceptually.

```kotlin
// creating a list
val innerPlanets = listOf("Mercury", "Venus", "Earth", "Mars")

//creating an array list
val innerPlanetsArrayList =
arrayListOf("Mercury", "Venus", "Earth", "Mars")

// creating an empty list
val subscribers: List<String> = listOf()
val subscribers = listOf<String>()
```

**Mutable List**
This is a type of list that can be altered

```kotlin
// creating a mutable list
val outerPlanets =
mutableListOf("Jupiter", "Saturn", "Uranus", "Neptune")

//creating an empty list
val exoPlanets = mutableListOf<String>()

// accessing element in mutable list
val players = mutableListOf("Alice", "Bob", "Cindy", "Dan")

print(players.isEmpty()) // > false

if (players.size < 2) {
println("We need at least two players!")
} else {
println("Let's start!")
} // > Let's start!

//returning the first element of the list
println(players.first()) // Alice

// return the last element
println(players.last()) // Dan

//using Indexes
println(players[0]) // Alice
print(players.get(1)) // Bob

//using range to slice
print(players.slice(1..2)) //Bob,Cindy

//Modify list
players.add("Breanna")
players += "Nelly"
println(players.joinToString())

// insert element at a specific index
players.add(5,"John")

// to remove element
players.remove("Bob")  // returns a boolean

// remove element with index
players.removeAt(2) // Cindy

// updating a list
players[4] = "Franklin"

```
</details>

<details>
<summary>Nullability</summary>

Nullables are Kotlin’s solution to the problem of representing both a
value and the absence of a value. A nullable is allowed to hold either a
value or null.

a `?` is used to show that the variable can be null or hold a value

```kotlin
// Declearing a variable nullable
var errorCode: Int?
```
**Null-assertion operator (!!)**

Is an operator used to remove the nullable from a variable

```kotlin
var currentAge:Int? = 22
var afterBirthday:Int = currentAge!!+1

println("Age after birthday is $afterBirthday") // 23

var age = null
println("After birthday age is ${age+1}") //returns KotlinNullPointerException

//To avoid exception do smartcast
if(age != null){
    println("After birthday age is ${age+1}")
} else{
    println("No value is set")
}
```

**Safe call(?.)**

This give the capability to perform action on a nullable variable e.g accessing the length.

```kotlin
val className:Int? = "Grade 7"
val classLength = className?.length?.plus(5)

// another way to smart cast is by using the let() function
className?.let {
classLength = className.length
}
```

**Elvis operator (?:)**

Elvis operator is used when you want to get a value out of the nullable no matter what and in the case of null, you’ll use a default value.

```kotlin
    var num:Int? = null
    var numMustHaveValue:Int?  = num ?:0
```


</details>

<details>
<summary>Maps and Set</summary>
</details>

<details>
<summary>Functions</summary>
Functions are used to perform actions.
Functions are defined using the `fun` keyword.
After we have defined a function we call it in the code.

```kotlin
fun functionName(parameter: dataType) {
    // function body
}
```
**Function parameter**

parameter provide input to our functions.

```kotlin
fun functionName(parameter: dataType) {
    // function body
}

fun printMultipleOfFive(value: Int) {
println("$value * 5 = ${value * 5}")
}
printMultipleOfFive(10)
```
To call the function we use the function name followed by the arguments.

```kotlin
functionName(argument)
```
We can provide multiple arguments to a function.

```kotlin
fun functionName(parameter1: dataType, parameter2: dataType) {
    // function body
}

fun printMultipleOf(multiplier: Int, andValue: Int) {
println("$multiplier * $andValue = ${multiplier * andValue}")
}
printMultipleOf(4, 2)
```

**Parameter named arguments**

```kotlin
   printMultipleOf(multiplier = 4, andValue = 2)
```

**Parameter default values**

```kotlin
fun printMultipleOf(multiplier: Int, value: Int = 1) {
println("$multiplier * $value = ${multiplier * value}")
}
printMultipleOf(4)
printMultipleOf(4,7)
```

**Function return values**

Functions can return values using the `return` keyword.

```kotlin
fun sum(a: Int, b: Int): Int {
    return a + b
}

//inline function
fun multiplyInferred(number: Int, multiplier: Int) = number * multiplie
```

**Parameter as Value**

Function parameters are constants by default, which means they can’t be modiﬁed.

```kotlin
fun incrementAndPrint(value: Int) {
value += 1
print(value)
}

// Correct way to do it 
fun incrementAndPrint(value: Int): Int {
 val newValue = value + 1
 println(newValue)
 return newValue
}
```
>>Output Val cannot be reassigned.

**Function Overloading**

Function overloading is having more than one function name with different implementation but same name

```kotlin
fun getValue(value: Int): Int {
return value + 1
}
fun getValue(value: String): String {
return "The value is $value"
}
```
Function overloading is achived through
- A different number of parameters.
- Different parameter types.

**Function as a variable**

Functions in Kotlin are simply another data type. You can assign them to variables and constants

To assign a function to a variable used the `method reference operator (::)`

```kotlin
// function
fun add(a: Int, b: Int): Int {
return a + b
}

// assigning function to a variable
var sumFunction = ::add()

// using the variable
sumFunction(2,7)
```

**Lambda Functions / Anonymous Function**

Anonymous functions are used to create a function without a name. They are just assigned variable which is passed around like any value.

```kotlin  
//declare
val sum: (Int, Int) -> Int

//assign
 sum = { x, y -> x + y }

 declare and assign
 val sum:(Int,Int) -> Int = { x, y -> x + y }

```
`it` is used for a lambda with only one parmeter.

```kotlin
val double = {
    a:Int -> 2*it
}

val square = {
    a:Int -> it*it
}
```


**High-order functions**

A higher order function is a function that takes a function as an argument.

```kotlin
fun apply(x:Int, action: (Int) -> Int): Int {
    return action(x)
}
```
`filter()` function of an array takes a boolean function and returns the elements that satisfy the condition.

```kotlin
val nums = arrayOf(1, 2, 3, 4, 5)
val evenNums = nums.filter { it % 2 == 0 }
println(evenNums)
```

</details>


## Object Oriented programming

OOP is a programming paradigm that focuses on the use of object to represent real-world enitites.

In OOP object is an instance of class and the class is the blueprint of an object which conatins the object data and function.

<details>
<summary>Classes</summary>
Class is a blueprint or template for creating an object, it defines the properties and methods the object will have.

Class is said to be a `Reference type`. This means a variable of a class type does not store an actual instance, but a reference to a location in memory that stores the instance.

When we have our class defined, we can create objects from it.

```kotlin
// class with a default constructor
class Dog {
    var name = ""
    var breed = ""
    fun bark() {
        println("Woof")
    }
}

// class with a constructor
class Dog(val name:String, val breead:String){
    fun bark() {
        println("Woof")
    }
}
```
</details>

<details>
<summary>Constructors</summary>
Constructors are used to initialize the values of the properties of a class.

```kotlin
// primary constructor
class User(var name: String, var age: Int) {
    init {
        println("User created: $name, $age")
    }
}

// you can also used key word constructor
class User constructor(var name: String, var age: Int) {
    init {
        println("User created: $name, $age")
    }
}
```

Now when creating a new object from the class, we can provide the values for the properties.

```kotlin
val user = User("John", 30)
println(user.name)
```

Kotlin allows you to create multiple constructors using the `constructor` keyword.

```kotlin
// creating secondary constructor. 
class User{
    constructor(name: String) {
        println("User created: $name")
    }
    constructor(name: String, age: Int) {
        println("User created: $name, $age")
    }
}
```
Our user has two constructors
</details>

<details>
<summary>Data Classes</summary>
This is a class that gives the capability of comparing two different objects of class, printing and even creating a copy of.

Most time data class are used to create the `DTO` or `POJO` classes

How to create a data class we use the key word `data` 

```kotlin
   data class StudentData(
     var ﬁrstName: String,
     var lastName: String,
     var id: Int
)

// creating different instances

val mercy = StudentData("Mercy", "Curie", id = 1)
val grace = StudentData("Grace", "Nelly", id = 2)

// create a copy of
val mercyCopy = mercy.copy()

// print a class
println(grace) ---> StudentData("Grace", "Nelly", id = 2)

// do comparison
println(mercy == grace)  ---> False
println(mercy == mercyCopy) ---> True
```

**Destructuring declarations**
Give the capabilty of extracting a data within a data class

```kotlin
val (ﬁrstName, lastName, id) = grace
 println(ﬁrstName) // > Grace
 println(lastName) // > Nelly
 println(id)
```
</details>

<details>
<summary>Object Classes</summary>
object is used to denote a custom type that can only have
a single instance.

The `object` keyword lets you easily implement a common
pattern in software development: The singleton pattern. 

It lets you deﬁne a type that only has a single instance — a named object.

`companion object` is used to create static members within your class.

**Singletons**

Singleton is used when you want to restrict a class to have a single instance during any given run of an application.

```kotlin
// creating an object class with several functions 
object StudentRegistry {
    val allStudents = mutableListOf<Student>()
    fun addStudent(student: Student) {
        allStudents.add(student)
    }
    fun removeStudent(student: Student) {
        allStudents.remove(student)
    }
    fun listAllStudents() {
        allStudents.forEach {
        println(it.fullName)
    }
  }
}

// use object to provide a namespace for constants that need to be referenced from multiple places in your app

object Constants{
    const val BASE_URL ="https......"
    const val LOGIN_ENDPOINT = "login"
}
```

**Anonymous Object**

Anonymous classes are used in Java to override the behavior of existing classes without the need to subclass, and also to implement interfaces without deﬁning a concrete class

How to create an anonymous class

```kotlin
interface Counts {
  fun studentCount(): Int
  fun scientistCount(): Int
}

val counter = object : Counts {
   override fun studentCount(): Int {
      return StudentRegistry.allStudents.size
   }
   override fun scientistCount(): Int {
      return ScientistRepository.allScientists.size
   }
}
println(counter.studentCount()) // > 3
println(counter.scientistCount()) // > 3
```

</details>

<details>
<summary>Abstract Classes</summary>

Abstract class are class that can be inherited but not instantiated.

```kotlin
abstract class Mammal(val birthDate: String) {
        abstract fun consumeFood()
}

class Human(birthDate: String): Mammal(birthDate) {
    override fun consumeFood() {
        // TODO()
    }
    fun createBirthCertiﬁcate() {
        //TODO()
    }
}
```
</details>

<details>
<summary>Nested and Inner Classes</summary>
Inner class or nested classes is when a class in defined within the scope of another class.

`inner` is used to define a nested class it enables the class to have access to other members. 

```kotlin
class Car(val carName: String) {
  inner class Engine(val engineName: String) {
    override fun toString(): String {
r       return "$engineName engine in a $carName"
    }
 }
}

val mazda = Car("mazda")
val mazdaEngine = mazda.Engine("rotary")
println(mazdaEngine) // > rotary engine in a mazda
```

</details>

<details>
<summary>Sealed And Enum Classes</summary>

**Sealed Classes**

Sealed classes are useful when you want to make sure that the values of a given data can only come from a particular limited set of subtypes

**Key point to Note on Sealed class**

- Sealed class are `abstract` it means it cannot instantiated directly,only one of the declared subclass.
- Sealed class can have abstract members which must be implemented by all the subclass of a sealed class.
- Unlike enum classes, where each case is a single instance of the class, you can have multiple instances of a subclass of a sealed class.
- You can’t make direct subclasses of a sealed class outside of the ﬁle where it’s declared, and the constructors of sealed classes are always private.
- 

```kotlin
// creating a sealed class
sealed class Shape {
    class Circle(val radius: Int): Shape()
    class Square(val sideLength: Int): Shape()
    class Rectangel(val sideLength: Int): Shape()

    // to print the shape name
    val name:String
    get() = when(this){
        is Circle -> "Circular"
        is Square -> "Square"
        is Rectangel -> "Rectangular"
    }
}


// creating sealed class with abstract member
sealed class Shape {
    abstarct val valueInFloat:Float
    var size:Float = 2.8f
    class Circle(val radius: Int): Shape(){
        override val valueInFloat = 7.0f
    }
    class Square(val sideLength: Int): Shape(){
        override val valueInFloat = 8.0f
    }
    class Rectangel(val sideLength: Int): Shape(){
        override val valueInFloat = 9.0f
    }

    fun totalSizeInFloat():Float{
        return size * valueInFloat
    }

}

// should be done within the main function

// creating instance of sealed subclass.
val circle1 = Shape.Circle(4)
val circle2 = Shape.Circle(2)
val square1 = Shape.Square(4)
val square2 = Shape.Square(2)

// printing the shape name using the class instance
println("The shape name is ${circle1.name}")

// using class instant to change the size value
circle1.size = 2.5f

//print the shape total value
println("The shape total size is ${circle1.totalSizeInFloat()}")
```
**Enum Classes**

In programming language `enum` is used to indicate that something has number of possible values.

In kotlin enum is created by creating an enum class.

```kotlin
// creating enum class
enum class DaysOfWeek{
    Sunday,
    Monday,
    Tuesday,
    Wednesday,
    Thursday,
    Friday,
    Saturday
}

// within the main function
    for (day in DaysOfWeek.values()) {
        println("Day ${day.ordinal}: ${day.name}")
    }

    //value() --> companion function within the enum class which give access to list of delared cases in the class

    // ordinal --> give the index of the declared cases
    // name --> give the name of the declared cases



    // getting the value at a specified index
    val dayIndex = 0
    val dayAtIndex = DaysOfWeek.values()[dayIndex]
    println("Day at $dayIndex is $dayAtIndex")

    // getting the index of specified value
    val tuesday = DaysOfWeek.valueOf("Tuesday")
    println("Tuesday is day ${tuesday.ordinal}")

```

**Enum class properties and functions**

```kotlin
enum class DaysOfWeeK(val isWeekend:Boolean = false){
    Monday,
    Tuesday,
    Wednesday,
    Thursday,
    Friday,
    Saturday(true),
    Sunday(true);
}

 for (day in DaysOfWeek.values()) {
       println("Day ${day.ordinal}: ${day.name}, is weekend: ${day.isWeekend}")
}
```
enum classes have companion object to do task or things that don't depend on a specife instance of class.

```kotlin
companion object{
    fun today() : DaysOfWeek{
    // using calender instance to get current day of week
    val calendarDayOfWeek = Calendar.getInstance().get(Calendar.DAY_OF_WEEK)

    // subtracting 2: 1 to account for the indexing change, and 1 to account for the difference of the ﬁrst day of the week.
    var adjustedDay = calendarDayOfWeek - 2

    val days = DayOfTheWeek.values()
    if (adjustedDay < 0) {
        adjustedDay += days.count()
    }
    val today = days.ﬁrst { it.ordinal == adjustedDay }
    return today
  }
}

// enum with when
    when (today) {
        DaysOfWeek.Monday -> println("I don't care if $today's blue")
        DaysOfWeek.Tuesday -> println("$today's gray")
        DaysOfWeek.Wednesday -> println("And $today, too")
        DaysOfWeek.Thursday -> println("$today, I don't care 'bout you")
        DaysOfWeek.Friday -> println("It's $today, I'm in love")
        DaysOfWeek.Saturday -> println("$today, Wait...")
        DaysOfWeek.Sunday -> println("$today always comes too late")
        else -> println("I don't feel like singing")
    }
```


</details>

<details>
<summary>Interfaces</summary>

Interfaces are a way of defining a set of methods that a class can implement in order to provide a specific set of behaviour.

```kotlin
interface Animals{
    fun sounds()
    fun names()
    fun breed()
}
```

</details>

<details>
<summary>Generics</summary>
Centralizing code to save time and prevent bug is a big issue in programming language.You need to create one place where all changes are done and can also only be broken at one place.

A helpfull feature in kotlin to this is `generics`. 

The general concept of generic programming is that you don’t necessarily need to know exactly what type an object is or even the type of other object it is associated with.

```kotlin
// creating a generic function

/*
 a function that takes array of any type and element of any type simillar to array type and finds the element 
*/
    fun <T> findElement(
    array: Array<T>,
    element: T,
    foundElement: (index: Int, element: T?) -> Unit
){
    for(i in array.indices){
        if(array[i] == element){
            foundElement(i,array[i])
            return
        }
    }
    foundElement(-1,null)
    return
}

// creating a generic class
class ArrayUtil<T>(private val array:Array<T>) {
    fun findElement(element:T, foundElement:(index:Int, element:T?) ->Unit){
        for(i in array.indices){
            if(array[i] == element){
                foundElement(i,array[i])
                return
            }
        }
        foundElement(-1,null)
        return
    }
}

```


</details>

<details>
<summary>Properties</summary>
These are the variable defined within a class and describes the characteristics of an object.
These properties are accessed and manipulated using the (.) operator.

***Constructor properties it can have default values***

```kotlin
class Contact(
    var fullName: String,
    val emailAddress: String,
    var type: String = "Friend" // has a default value
)
```
***Property initializers***

Give the capabilty to initialize a property outside a primary constrator using the values passed in the constuctor.

```kotlin
class Person(val ﬁrstName: String, val lastName: String) {
    val fullName = "$ﬁrstName $lastName" // property intialized.
}
```
***Custom accessors***

The ability to define your custom get and set methods

```kotlin
class TV(var height: Double, var width: Double) {
  val diagonal: Int
    get() {
    val result = Math.sqrt(height * height + width * width)
    return result.roundToInt()
    }
    set(value) {
    val ratioWidth = 16.0
    val ratioHeight = 9.0
    val ratioDiagonal = Math.sqrt(
    ratioWidth * ratioWidth + ratioHeight * ratioHeight
    )
    height = value.toDouble() * ratioHeight / ratioDiagonal
    width = height * ratioWidth / ratioHeight
    }
}


val tv = TV(height = 53.93, width = 95.87)
val size = tv.diagonal // calls the get method.
tv.diagonal = 55 // set method
```

***Delegated properties***

Delegated properties, are indicated with the use of the `by` keyword.

    - lazy property
    - observable property

***Extension property***

Extension properties allow you to add properties to a class outside of
the class deﬁnition, for example, if you’re using a class from a library.

```kotlin
// creates an extension property named diameter on the Circle class
    val Circle.diameter: Double
        get() = 2.0 * radius
```

***lateinit***

lateinit can be used to defer setting the value of a property reference until after the instance is created.
</details>



### Main Principle of OOP
- Encapsulation
- Inheritance
- Polymophism

<details>
<summary>Inheritance</summary>

Inheritance is when a class is derived from another class, the child class inherits all the public and protected properties and methods of a parent class

`:` is used to show inheritance
The keyword `open` is used to create an inheritable class

```kotlin
// super/base class
open class Person(var ﬁrstName: String, var lastName: String) {
fun fullName() = "$ﬁrstName $lastName"
}

// sub/derived class that inherits the base class
class Student(ﬁrstName: String,lastName: String,
  var grades: MutableList<Grade> = mutableListOf<Grade>()
) : Person(ﬁrstName, lastName) {
open fun recordGrade(grade: Grade) {
grades.add(grade)
 }
}
```
### Rules for subclassing
- A Kotlin class can inherit from only one other class, a concept known as single inheritance.
- A Kotlin class can only inherit from a class that is open.
- There’s no limit to the depth of subclassing, meaning you can
subclass from a class that is also a subclass, like below (and ﬁrst
redeﬁning Student with open)

a chain of class is called `class hierarchy`

```kotlin
open class Student(ﬁrstName: String,lastName: String,
var grades: MutableList<Grade> = mutableListOf<Grade>()
) : Person(ﬁrstName, lastName) {
open fun recordGrade(grade: Grade) {grades.add(grade)}
}
open class BandMember(ﬁrstName: String,lastName: String) : Student(ﬁrstName, lastName) {open val minimumPracticeTime: Int
get() { return 2 }
}
class OboePlayer(ﬁrstName: String,lastName: String):BandMember(ﬁrstName, lastName) {
// This is an example of an override, will be covered soon.
override val minimumPracticeTime: Int =
super.minimumPracticeTime * 2
}
```
</details>

<details>
<summary>Polymophism</summary>
`Poly` means many `moph` means form so polymophism is the ability to take many form.

- method overriding
- method overloading
</details>

<details>
<summary>Encapsulation</summary>
Encapsulation is information hiding. In oop information can be hidden using :-
 
 - Access Modifiers
 - Creating interfaces
</details>


### Object
Object is an instance of a class with specific alue and properties, a class defines the property and methods that an object will have

```kotlin
//object with default constructor
val dog = Dog()

// object with parameterised constractor
val person = User("Ken",15)
```

### Access Modifiers
- #### Public
    The class and it public methods can be accessed by any one who see it
- #### Private
    Means that the members are visible within the class only
- #### Protected       
    means that the members have visibility simillar to `private` but it is also visible to its subclasses.
- #### internal
    Any client within the module that sees the declared class sees its internal members.




