# scala-notes
My notes on scala
##Install
* Obtain software from www.scala-lang.org
* Unzip it and you are good to go

# Basic good to know
* Scala is statically typed language
*

# Simple  instantiation
```scala
class Hello {
  def hello() = println("hello Ashoka!!!");
}

val h = new Hello();  // this is a contant/final declaration
var h2 = new Hello();  // this is a variable declaration
h.hello();
h2.hello();
```

# Constructor with arguments
```scala
class Hello(message: String) {
  def hi() = println(message)
  println("How are you?")
}

val hello = new Hello("Hello Ashok!")
hello.hi()
```


```scala
class Hello(message: String, secondaryMessage: String) {
    def this(message: String) = this(message, "")
    
    def hi() = println(message + secondaryMessage)
}

val hello = new Hello("Hello Ashoka!")
hello.hi()
val hello2 = new Hello("Hello Ashoka!", " How are you?")
hello2.hi()
```

# Inheritence classes -- Need to debug further
```scala
abstract class Hello {
  var msg: String
  def hi() = println(msg)
}

class HelloChild extends Hello {
  msg = "hello from Child!";
}

val hello = new HelloChild();
hello.hi()

```

# Methods
**def methodName(param1: param1Type, param2: param2Type) : returnType = { method body }**

* The value of the last statment is returned by default

```scala
def compute(x: Int, y: Int) = {
   if (x > y)
     return (x + y) // explicit return

   (x - y)          // implicit return
}
```
## Named argument in methods
```scala
class Hello(guest: String) {
    def hi() = {
      println("Hello!")
    }
    
    def hi(to: String) = {
      println("Hi " + to)
    }
    
    def intro() = {
      println("My name is " + guest)
    }
}

val h = new Hello("Ashok"); 
h.hi();
h.intro();
h.hi(to = "Anirudha")
```


# Conditionals
```scala
genderString = if(emp.male) "Male" else "Female"
```

# Collection
```scala
class FamilyMember (val name: String, val isMale: Boolean)
val family = List(
  new FamilyMember("Ashok", isMale=true),
  new FamilyMember("Nirmala", isMale=false),
  new FamilyMember("Anirudh",isMale = true),
  new FamilyMember("Avanish", isMale = true));

// Printing all member names
for(member <- family) println(member.name)

// Filter females in the family
for(member <- family 
    if !member.isMale) 
  println(member.name)
    
// Print all names that contain 'i' in it
for(member <- family
    if member.name.contains("i"))
    println (member.name)
    
// Print all names that starts with A and contains 'i' in it
for(member <- family
    if member.name.startsWith("A")
    if member.name.contains("i"))
    println (member.name)

// Combinations of two lists
val guests = List(
  new FamilyMember("Guest1",isMale = true),
  new FamilyMember("Guest2", isMale = false));

// Combination of family & guests
for(member <- family; guest <- guests)
  println("Speech session: " +member.name +", " +guest.name)
  
// extract an attribute from all elements in a list into a collection  
val memberNames = for(member <- family) yield member.name
for (name <- memberNames)  println(name)
```
