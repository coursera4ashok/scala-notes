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
~ def methodName(param1: param1Type, param2: param2Type) : returnType = { method body }

* The value of the last statment is returned by default

```scala
def compute(x: Int, y: Int) = {
   if (x > y)
     return (x + y) // explicit return

   (x - y)          // implicit return
}
```
