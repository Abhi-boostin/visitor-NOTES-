# MOOC JAVA NOTES

## PART 1
### Getting started with programming
Here are some things you learned:

How to install the necessary software for programming in Java<br>
The basics of programming<br>
How to use the Eclipse IDE

```java
public class HelloWorld {
  public static void main(String[] args) {
    System.out.println("Hello, World!");
  }
}
```
### Printing
This is an article about teaching Java programming. It discusses printing text to the console. The important thing they teach is that programmers should use comments to make their code easier to understand. They also teach that programmers should use semicolons to separate commands.

### Reading Inputs

```java
// Introduce the scanner tool used for reading user input
import java.util.Scanner;

public class Program {

    public static void main(String[] args) {
        // Create a tool for reading user input and name it scanner
        Scanner scanner = new Scanner(System.in);

        // Print "Write a message: "
        System.out.println("Write a message: ");

        // Read the string written by the user, and assign it
        // to program memory "String message = (string that was given as input)"
        String message = scanner.nextLine();

        // Print the message written by the user
        System.out.println(message);
    }
}
```
```java
    String message = "Hello world!";
System.out.println("message"); 
```
In general, you should use the scanner.nextLine() method if you need to perform additional processing on the input stream, such as skipping whitespace characters or delimiting tokens. If you simply need to read a line of text from the input stream, you can use either the reader.nextLine() method or the scanner.nextLine() method.

```java
//Introduce the Scanner tool used for reading
import java.util.Scanner;

public class Program {

    public static void main(String[] args) {

        //Create the tool for reading, assign it to variable caller "scanner
        Scanner scanner = new Scanner(System.in);

        //Print user a message "Write a message: "
        System.out.println("Write a message: ");

        //Read the user's string input, save it to program memory
        //"String message = (user input)"
        String message = scanner.nextLine();

        // Print the user input twice
        System.out.println(message);
        System.out.println(message);
    }
}
```
### variable 
Variables are used to store data in Java.
There are eight primitive data types in Java: byte, short, int, long, float, double, char, and boolean.
Variables are declared using the var keyword, followed by the variable name and data type.
Variables are initialized using the assignment operator (=).
Variable names should be descriptive and start with a lowercase letter.
```java
int number = 123;
System.out.println("The value of the variable is " + number);

number = 42;
System.out.println("The value of the variable is " + number);
```
```java
String valueAsString = "42";
int value = Integer.valueOf(valueAsString);

System.out.println(value);
```
Boolean.valueOf.

Boolean variables can either have the value true or false. When converting a string to a boolean, the string must be "true" if we want the boolean value to be true. The case is insensitive here: both "true" and "TRue" turn into the boolean value of true. All other strings turn into the boolean false.

### Calculating with numbers
BODMAS
integer division gives the integer output nearest roundoff
if one of them is float the answer will be in float
also
```java
int first = 3;
int second = 2;

double result1 = (double) first / second;
System.out.println(result1); // prints 1.5

double result2 = first / (double) second;
System.out.println(result2); // prints 1.5

double result3 = (double) (first / second);
System.out.println(result3); // prints 1.0
```
The last example produces an incorrectly rounded result, because the integer division is executed before the type casting.

### Conditional statements and conditional operation
The comparisons are executed top down. When execution reaches a conditional statement whose condition is true, its block is executed and the comparison stops.

Even though we can compare integers, floating point numbers, and boolean values using two equals signs (variable1 == variable2), we cannot compare the equality of strings using two equals signs.

```java
if (input.equals("a string")) {
    System.out.println("Great! You read the instructions correctly.");
} else {
    System.out.println("Missed the mark!");
}
```
and &&, or ||, and not ! are used.

## PART 2
### Recurring problems and patterns to solve them
If the variable used to store the data is introduced within the loop, the variable is only available within that loop and nowhere else.
### more loops
```java
for (int i = 0; i < 10; i++) {
    System.out.println(i);
}
```
1) introducing the variable for counting the number of executions; <br>(2) the condition of the loop; <br>(3) increasing (or decreasing or changing) the value of the counter variable; and <br>(4) the functionality to be executed.
 ```java
 result += 3; // shorthand for result = result + 3
 ```
 ### Methods and dividing the program into smaller parts
 The void keyword specifies that a method should not have a return value.
 
 Static:- it is access modifier that means when the java program is load then it will create the space in memory automatically.

The return value does not need to be entirely pre-defined - it can also be calculated. The return command that returns a value from the method can also be given an expression that is evaluated before the value is returned.

As we noticed earlier, other methods can be called from within methods.

## PART 3
### Discovering errors
### Lists
import java.util.ArrayList; 
```java
// import the list so the program can use it
import java.util.ArrayList;

public class Program {

    public static void main(String[] args) {
        // create a list
        ArrayList<String> list = new ArrayList<>();

        // the list isn't used yet
    }
}
```
get() <br> add() <br> remove() <br> size() <br> isEmpty() <br> clear()

f you try to retrieve information from a place that does not exist on the list, the program will print a IndexOutOfBoundsException error.
```java
ArrayList<String> teachers = new ArrayList<>();


teachers.add("Simon");
teachers.add("Samuel");
teachers.add("Ann");
teachers.add("Anna");

for (String teacher: teachers) {
    System.out.println(teacher);
}
```
```java
int[] numbers = new int[3];
```
```java
Scanner reader = new Scanner(System.in);

int[] numbers = new int[5];
numbers[0] = 42;
numbers[1] = 13;
numbers[2] = 12;
numbers[3] = 7;
numbers[4] = 1;

System.out.println("Which index should we access? ");
int index = Integer.valueOf(reader.nextLine());

int number = numbers[index];
System.out.println(number);
```
length <Br>
ArrayIndexOutOfBoundsException.<Br>
(typeofelements[])
```java
 String[] months = new String[12]
 double[] approximations = new double[100];
```
```java
public static void listElements(int[] integerArray) {
    System.out.println("the elements of the array are: ");
    int index = 0;
    while (index < integerArray.length) {
        int number = integerArray[index];
        System.out.print(number + " ");
        index = index + 1;
    }

    System.out.println("");
}   
```
```java
int[] numbers = {100, 1, 42}; ///shorter way to create an array
```
### Using strings
```java
tring text = "first second third fourth";
String[] pieces = text.split(" ");
System.out.println(pieces[0]);
System.out.println(pieces[1]);
System.out.println(pieces[2]);
System.out.println(pieces[3]);

System.out.println();

for (int i = 0; i < pieces.length; i++) {
    System.out.println(pieces[i]);
}
```
String.contains()
## PART 4
### Introduction to object-oriented programming
CLASS
```java
public class Person {
    private String name;
    private int age;
}
```
METHOD
```java
public class Person {
    private String name;
    private int age;

    public Person(String initialName) {
        this.age = 0;
        this.name = initialName;
    }
}
```
```java
public class Person {
    private String name;
    private int age;

    public Person(String initialName) {
        this.age = 0;
        this.name = initialName;
    }

    public void printPerson() {
        System.out.println(this.name + ", age " + this.age + " years");
    }
}
```
### Objects in a list
### Files and reading data
file reading 
try and catch
```java
// we create a scanner for reading the file
try (Scanner scanner = new Scanner(Paths.get("henkilot.csv"))) {

    // we read all the lines of the file
    while (scanner.hasNextLine()) {
        String line = scanner.nextLine();

        // if the line is blank we do nothing
        if (line.isEmpty()) {
            continue;
        }

        // do something with the data

    }
} catch (Exception e) {
    System.out.println("Error: " + e.getMessage());
}
```
### Part 5
#### Learning object-oriented programming
Object-oriented programming is primarily about isolating concepts into their own entities or, in other words, creating abstractions

class
A class defines the types of objects that can be created from it. It contains instance variables describing the object's data, a constructor or constructors used to create it, and methods that define its behavior. A rectangle class is detailed below which defines the functionality of a rectangle.

 <br>  constructor <br> object

### Removing repetitive code (overloading methods and constructors)

```java
public Person(String name) {
    this(name, 0);
    //here the code of the second constructor is run, and the age is set to 0
}

public Person(String name, int age) {
    this.name = name;
    this.age = age;
    this.weight = 0;
    this.height = 0;
}
```
### Primitive and reference variables
```java
Name luke = new Name("Luke");
System.out.println(luke);

///Sample output
///Name@4aa298b7
```
public String toString()

Reference Variables
All of the variables provided by Java (other than the eight primitive variables mentioned above) are reference type. A programmer is also free to create their own variable types by defining new classes. In practice, any object instanced from a class is a reference variable.

### Objects and references
```java
public class Person {

    private String name;
    private int age;
    private int weight;
    private int height;

    public Person(String name) {
        this(name, 0, 0, 0);
    }

    public Person(String name, int age, int height, int weight) {
        this.name = name;
        this.age = age;
        this.weight = weight;
        this.height = height;
    }

    // other constructors and methods

    public String getName() {
        return this.name;
    }

    public int getAge() {
        return this.age;
    }

    public int getHeight() {
        return this.height;
    }

    public void growOlder() {
        this.age = this.age + 1;
    }

    public void setHeight(int newHeight) {
        this.height = newHeight;
    }

    public void setWeight(int newWeight) {
        this.weight = newWeight;
    }

    public double bodyMassIndex() {
        double heightPerHundred = this.height / 100.0;
        return this.weight / (heightPerHundred * heightPerHundred);
    }

    @Override
    public String toString() {
        return this.name + ", age " + this.age + " years";
    }
}
```
Person ball = joan;
null value of a reference variable
Printing a null reference prints "null". How about if we were to try and call a method, say growOlder, on an object that refers to nothing:

NullPointerException.

Object as a method's return value
```java
public class Counter {
    private int value;

    // example of using multiple constructors:
    // you can call another constructor from a constructor by calling this
    // notice that the this call must be on the first line of the constructor
    public Counter() {
        this(0);
    }

    public Counter(int initialValue) {
        this.value = initialValue;
    }

    public void increase() {
        this.value = this.value + 1;
    }

    public String toString() {
        return "value: " + value;
    }

    public Counter clone() {
        // create a new counter object that receives the value of the cloned counter as its initial value
        Counter clone = new Counter(this.value);

        // return the clone to the caller
        return clone;
    }
}
```
## PART 6
### Objects on a list and a list as part of an object
Objects in an Instance Variable List
Printing an Object from a List
Clearing an Object's List
Calculating a Sum from Objects on a List
### Separating the user interface from program logic
Looping and quitting

Proceed with small steps

Try to separate the program into several sub-problems and work on only one sub-problem at a time
Always test that the program code is advancing in the right direction, in other words: test that the solution to the sub-problem is correct
Recognize the conditions that require the program to work differently. In the example above, we needed a different functionality to test whether a word had been already entered before.
Write as "clean" code as possible

Indent your code
Use descriptive method and variable names
Don't make your methods too long, not even the main method
Do only one thing inside one method
Remove all copy-paste code
Replace the "bad" and unclean parts of your code with clean code
### Introduction to testing
Stack Trace

Indent your code properly and find out if there are any missing parentheses.
Verify that the variables used are correctly named.
Test the program flow with different inputs and find out the sort of input that causes the program to not work as desired. If you received an error in the tests, the tests may also indicate the input used.
Add print commands to the program in which you print out the values of the variables used at various stages of the program's execution.
Verify that all variables you are using are initialized. If they aren't, a NullPointerException error will occur.
If your program causes an exception, you should definitely pay attention to the stack trace associated with the exception, which is the list of method calls that resulted in the situation that caused the exception.
Learn how to use the debugger. The earlier video will get you started.

Unit Testing

### Complex programs

## PART 7
### Programming paradigms
A programming paradigm is a way of thinking about and structuring a program's functionality. Programming paradigms differ from one another, for example in how the program's execution and control are defined and what components the programs consist of.

Most programming languages ​​that are currently in use support multiple programming paradigms. Part of a programmer's growth involves the ability, through experience, to choose the appropriate programming language and paradigm; there currently is no single ubiquitous programming language and programming paradigm.

The most common programming paradigms today are object-oriented programming, procedural programming, and functional programming. The first two of these are briefly discussed in what follows.
### Algorithms
Sorting information<br>
    Selection sort <Br>
    Linear search<br>
    Binary search<br>
### Larger programming exercises
### Conclusion
## PART 8
### Short recap
### Hash Map
A HashMap is, in addition to ArrayList, one of the most widely used of Java's pre-built data structures. The hash map is used whenever data is stored as key-value pairs, where values can be added, retrieved, and deleted using keys.
```java
HashMap<String, String> postalCodes = new HashMap<>();
postalCodes.put("00710", "Helsinki");
postalCodes.put("90014", "Oulu");
postalCodes.put("33720", "Tampere");
postalCodes.put("33014", "Tampere");

System.out.println(postalCodes.get("00710"));
```
put(*key*, *value*)<br>
get()
```java
Book book = directory.get("Persuasion");
System.out.println(book);
System.out.println();
book = directory.get("Pride and Prejudice");
System.out.println(book);
```
Hash Map as an Instance Variable<br>
Going Through A Hash Map's Keys
<br>Going Through A Hash map's Values
<br>default V getOrDefault(Object key, V defaultValue)
## Similarity of objects
Method to Test For Equality - "equals"<br>
```java
public class Book {
    private String name;
    private String content;
    private int published;

    public Book(String name, int published, String content) {
        this.name = name;
        this.published = published;
        this.content = content;
    }

    public String getName() {
        return this.name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getPublished() {
        return this.published;
    }

    public void setPublished(int published) {
        this.published = published;
    }

    public String getContent() {
        return this.content;
    }

    public void setContent(String content) {
        this.content = content;
    }

    public String toString() {
        return "Name: " + this.name + " (" + this.published +   ")\n"
            + "Content: " + this.content;
    }

    @Override
    public boolean equals(Object comparedObject) {
        // if the variables are located in the same place, they're the same
        if (this == comparedObject) {
            return true;
        }

        // if comparedObject is not of type Book, the objects aren't the same
        if (!(comparedObject instanceof Book)) {
            return false;
        }

        // let's convert the object to a Book-object
        Book comparedBook = (Book) comparedObject;

        // if the instance variables of the objects are the same, so are the objects
        if (this.name.equals(comparedBook.name) &&
            this.published == comparedBook.published &&
            this.content.equals(comparedBook.content)) {
            return true;
        }

        // otherwise, the objects aren't the same
        return false;
    }
}
```
Let's review the ideas once more: for a class to be used as a HashMap's key, we need to define for it:

the equals method, so that all equal or approximately equal objects cause the comparison to return true and all false for all the rest
the hashCode method, so that as few objects as possible end up with the same hash value

Grouping data using hash maps <br>
Fast data fetching and grouping information
## PART 9
### Class inheritance
```java
public class Engine extends Part {

    private String engineType;

    public Engine(String engineType, String identifier, String manufacturer, String description) {
        super(identifier, manufacturer, description);
        this.engineType = engineType;
    }

    public String getEngineType() {
        return engineType;
    }
}
```
Calling the constructor of the superclass
<br>Calling a superclass method
```java
@Override
public String toString() {
    return super.toString() + "\n  And let's add my own message to it!";
}
```
```java
public class Counter {

    public int addToNumber(int number) {
        return number + 1;
    }
    
    public int subtractFromNumber(int number) {
        return number - 1;
    }
}

----------------------

public class SuperCounter extends Counter {

    @Override
    public int addToNumber(int number) {
        return number + 5;
    }
    
}

----------------------

public static void main(String[] args) {
    Counter counter = new Counter();
    Counter superCounter = new SuperCounter();
    int number = 3;
    number = superCounter.subtractFromNumber(number);
    number = superCounter.subtractFromNumber(number);
    number = counter.addToNumber(number);
    System.out.println(number);
}
```
### Interfaces



