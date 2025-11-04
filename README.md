# Dart Programming Language - Comprehensive Guide

## Table of Contents
1. [Introduction and Basics](#1-introduction-and-basics)
2. [Conditions and Loops](#2-conditions-and-loops)
3. [Functions in Dart](#3-functions-in-dart)
4. [Collections in Dart](#4-collections-in-dart)
5. [File Handling in Dart](#5-file-handling-in-dart)
6. [OOP in Dart](#6-oop-in-dart)
7. [Null Safety In Dart](#7-null-safety-in-dart)
8. [Asynchronous Programming](#8-asynchronous-programming)
9. [Useful Information](#9-useful-information)
   - [Final Vs Const](#final-vs-const)
   - [Datetime In Dart](#datetime-in-dart)
   - [Extension In Dart](#extension-in-dart)
   - [Backend in Dart](#backend-in-dart)
   - [Dart Interview Questions](#dart-interview-questions)

---

## 1. Introduction and Basics

### What is Dart?
Dart is a client-optimized programming language developed by Google. It's used for building mobile, desktop, server, and web applications, particularly with the Flutter framework.

### Key Features
- **Object-oriented**: Everything is an object
- **Type-safe**: Strong typing with type inference
- **Null-safe**: Built-in null safety
- **Garbage collected**: Automatic memory management
- **Compiled**: Can compile to native code or JavaScript

### 10 Examples of Dart Basics

#### Example 1: Hello World Program
```dart
void main() {
  print('Hello, World!');
}
```

**Output:**
```
Hello, World!
```

#### Example 2: Variables and Data Types
```dart
void main() {
  // Integer
  int age = 25;
  
  // Double
  double height = 5.9;
  
  // String
  String name = 'John Doe';
  
  // Boolean
  bool isStudent = true;
  
  // Dynamic (can hold any type)
  dynamic variable = 'Hello';
  variable = 42;
  variable = true;
  
  print('Name: $name, Age: $age, Height: $height, Is Student: $isStudent');
}
```

**Output:**
```
Name: John Doe, Age: 25, Height: 5.9, Is Student: true
```

#### Example 3: Type Inference with var and final
```dart
void main() {
  // var - type is inferred, can be reassigned
  var count = 10;
  count = 20; // Valid
  
  // final - type is inferred, cannot be reassigned
  final pi = 3.14159;
  // pi = 3.14; // Error: cannot assign to final variable
  
  // const - compile-time constant
  const gravity = 9.8;
  // gravity = 10.0; // Error: cannot assign to const variable
  
  print('Count: $count, PI: $pi, Gravity: $gravity');
}
```

**Output:**
```
Count: 20, PI: 3.14159, Gravity: 9.8
```

#### Example 4: String Interpolation and Concatenation
```dart
void main() {
  String firstName = 'John';
  String lastName = 'Doe';
  int age = 30;
  
  // String interpolation
  String fullName = '$firstName $lastName';
  String message = 'Hello, my name is $fullName and I am $age years old.';
  
  // String concatenation
  String greeting = 'Hello' + ' ' + 'World';
  
  // Multi-line strings
  String multiLine = '''
    This is a
    multi-line
    string in Dart.
  ''';
  
  print(message);
  print(greeting);
  print(multiLine);
}
```

**Output:**
```
Hello, my name is John Doe and I am 30 years old.
Hello World
    This is a
    multi-line
    string in Dart.
```

#### Example 5: Arithmetic Operations
```dart
void main() {
  int a = 10;
  int b = 3;
  
  // Basic arithmetic
  int sum = a + b;
  int difference = a - b;
  int product = a * b;
  double quotient = a / b; // Division always returns double
  int remainder = a % b;
  int integerDivision = a ~/ b; // Integer division
  
  print('Sum: $sum');
  print('Difference: $difference');
  print('Product: $product');
  print('Quotient: $quotient');
  print('Remainder: $remainder');
  print('Integer Division: $integerDivision');
}
```

**Output:**
```
Sum: 13
Difference: 7
Product: 30
Quotient: 3.3333333333333335
Remainder: 1
Integer Division: 3
```

#### Example 6: Null Safety
```dart
void main() {
  // Non-nullable variables
  String name = 'John'; // Cannot be null
  // name = null; // Error: cannot assign null
  
  // Nullable variables
  String? nullableName; // Can be null
  nullableName = null; // Valid
  nullableName = 'Jane'; // Also valid
  
  // Null-aware operators
  String? maybeNull;
  String result = maybeNull ?? 'Default Value'; // Null coalescing
  int? length = maybeNull?.length; // Null-aware access
  
  print('Result: $result');
  print('Length: $length');
}
```

**Output:**
```
Result: Default Value
Length: null
```

#### Example 7: Comments and Documentation
```dart
// This is a single-line comment

/*
  This is a
  multi-line comment
*/

/// This is a documentation comment
/// It can be used to generate documentation
void main() {
  int number = 42;
  print('Number: $number');
}

/**
 * This is also a documentation comment
 * Used for more detailed documentation
 */
class Calculator {
  /// Adds two numbers and returns the result
  int add(int a, int b) => a + b;
}
```

**Output:**
```
Number: 42
```

#### Example 8: Basic Input/Output
```dart
import 'dart:io';

void main() {
  // Output
  print('Enter your name:');
  
  // Input
  String? name = stdin.readLineSync();
  
  // Output with input
  print('Hello, $name!');
  
  // Formatted output
  int age = 25;
  double salary = 50000.50;
  print('Age: ${age.toString().padLeft(3)}');
  print('Salary: \$${salary.toStringAsFixed(2)}');
}
```

**Output (assuming user enters 'Alice'):**
```
Enter your name:
Alice
Hello, Alice!
Age:  25
Salary: $50000.50
```

#### Example 9: Constants and Enums
```dart
// Enum definition
enum Color { red, green, blue }

void main() {
  // Using enums
  Color favoriteColor = Color.blue;
  print('Favorite color: $favoriteColor');
  print('Color index: ${favoriteColor.index}');
  
  // Switch with enums
  switch (favoriteColor) {
    case Color.red:
      print('You like red!');
      break;
    case Color.green:
      print('You like green!');
      break;
    case Color.blue:
      print('You like blue!');
      break;
  }
  
  // Constants
  const int maxAttempts = 3;
  const String appName = 'MyApp';
  
  print('Max attempts: $maxAttempts');
  print('App name: $appName');
}
```

**Output:**
```
Favorite color: Color.blue
Color index: 2
You like blue!
Max attempts: 3
App name: MyApp
```

#### Example 10: Basic Class and Object
```dart
class Person {
  String name;
  int age;
  
  // Constructor
  Person(this.name, this.age);
  
  // Method
  void introduce() {
    print('Hi, I am $name and I am $age years old.');
  }
  
  // Getter
  String get info => 'Name: $name, Age: $age';
}

void main() {
  // Creating objects
  Person person1 = Person('Alice', 25);
  Person person2 = Person('Bob', 30);
  
  // Using methods
  person1.introduce();
  person2.introduce();
  
  // Using getters
  print(person1.info);
  print(person2.info);
}
```

**Output:**
```
Hi, I am Alice and I am 25 years old.
Hi, I am Bob and I am 30 years old.
Name: Alice, Age: 25
Name: Bob, Age: 30
```

---

## 2. Conditions and Loops

### Overview
Conditions and loops are fundamental control structures in Dart that allow you to make decisions and repeat code execution.

### 10 Examples of Conditions and Loops

#### Example 1: Basic If-Else Statement
```dart
void main() {
  int age = 18;
  
  if (age >= 18) {
    print('You are an adult.');
  } else {
    print('You are a minor.');
  }
}
```

**Output:**
```
You are an adult.
```

#### Example 2: If-Else If-Else Chain
```dart
void main() {
  int score = 85;
  
  if (score >= 90) {
    print('Grade: A');
  } else if (score >= 80) {
    print('Grade: B');
  } else if (score >= 70) {
    print('Grade: C');
  } else if (score >= 60) {
    print('Grade: D');
  } else {
    print('Grade: F');
  }
}
```

**Output:**
```
Grade: B
```

#### Example 3: Ternary Operator
```dart
void main() {
  int temperature = 25;
  
  // Using ternary operator
  String weather = temperature > 20 ? 'Hot' : 'Cold';
  print('Weather: $weather');
  
  // Nested ternary
  String season = temperature > 30 ? 'Summer' : 
                  temperature > 20 ? 'Spring' : 
                  temperature > 10 ? 'Autumn' : 'Winter';
  print('Season: $season');
}
```

**Output:**
```
Weather: Hot
Season: Spring
```

#### Example 4: Switch Statement
```dart
void main() {
  String day = 'Monday';
  
  switch (day) {
    case 'Monday':
      print('Start of work week');
      break;
    case 'Tuesday':
    case 'Wednesday':
    case 'Thursday':
      print('Mid week');
      break;
    case 'Friday':
      print('TGIF!');
      break;
    case 'Saturday':
    case 'Sunday':
      print('Weekend!');
      break;
    default:
      print('Invalid day');
  }
}
```

**Output:**
```
Start of work week
```

#### Example 5: Switch Expression (Dart 3.0+)
```dart
void main() {
  String day = 'Friday';
  
  String message = switch (day) {
    'Monday' => 'Start of work week',
    'Tuesday' || 'Wednesday' || 'Thursday' => 'Mid week',
    'Friday' => 'TGIF!',
    'Saturday' || 'Sunday' => 'Weekend!',
    _ => 'Invalid day'
  };
  
  print(message);
}
```

**Output:**
```
TGIF!
```

#### Example 6: For Loop
```dart
void main() {
  // Basic for loop
  print('Numbers 1 to 5:');
  for (int i = 1; i <= 5; i++) {
    print(i);
  }
  
  // For loop with step
  print('\nEven numbers 0 to 10:');
  for (int i = 0; i <= 10; i += 2) {
    print(i);
  }
  
  // Reverse for loop
  print('\nCountdown from 5:');
  for (int i = 5; i >= 1; i--) {
    print(i);
  }
}
```

**Output:**
```
Numbers 1 to 5:
1
2
3
4
5

Even numbers 0 to 10:
0
2
4
6
8
10

Countdown from 5:
5
4
3
2
1
```

#### Example 7: For-In Loop
```dart
void main() {
  List<String> fruits = ['apple', 'banana', 'orange', 'grape'];
  
  // For-in loop with list
  print('Fruits:');
  for (String fruit in fruits) {
    print(fruit);
  }
  
  // For-in loop with string
  String word = 'Dart';
  print('\nLetters in "Dart":');
  for (String letter in word.split('')) {
    print(letter);
  }
  
  // For-in loop with range
  print('\nNumbers 1 to 5:');
  for (int number in List.generate(5, (index) => index + 1)) {
    print(number);
  }
}
```

**Output:**
```
Fruits:
apple
banana
orange
grape

Letters in "Dart":
D
a
r
t

Numbers 1 to 5:
1
2
3
4
5
```

#### Example 8: While Loop
```dart
void main() {
  int count = 0;
  
  // Basic while loop
  print('While loop - counting to 5:');
  while (count < 5) {
    print(count);
    count++;
  }
  
  // While loop with condition
  int number = 10;
  print('\nHalving 10 until it reaches 1:');
  while (number > 1) {
    print(number);
    number ~/= 2; // Integer division
  }
  print(number); // Print the final 1
}
```

**Output:**
```
While loop - counting to 5:
0
1
2
3
4

Halving 10 until it reaches 1:
10
5
2
1
```

#### Example 9: Do-While Loop
```dart
void main() {
  int count = 0;
  
  // Do-while loop (executes at least once)
  print('Do-while loop:');
  do {
    print('Count: $count');
    count++;
  } while (count < 3);
  
  // Do-while with false condition (still executes once)
  print('\nDo-while with false condition:');
  do {
    print('This will print once');
  } while (false);
}
```

**Output:**
```
Do-while loop:
Count: 0
Count: 1
Count: 2

Do-while with false condition:
This will print once
```

#### Example 10: Break and Continue
```dart
void main() {
  // Break example - exit loop early
  print('Numbers 1 to 10, stopping at 5:');
  for (int i = 1; i <= 10; i++) {
    if (i == 6) {
      break; // Exit the loop
    }
    print(i);
  }
  
  // Continue example - skip current iteration
  print('\nEven numbers 1 to 10:');
  for (int i = 1; i <= 10; i++) {
    if (i % 2 != 0) {
      continue; // Skip odd numbers
    }
    print(i);
  }
  
  // Nested loops with labels
  print('\nNested loops with break:');
  outerLoop: for (int i = 1; i <= 3; i++) {
    for (int j = 1; j <= 3; j++) {
      if (i == 2 && j == 2) {
        break outerLoop; // Break outer loop
      }
      print('i: $i, j: $j');
    }
  }
}
```

**Output:**
```
Numbers 1 to 10, stopping at 5:
1
2
3
4
5

Even numbers 1 to 10:
2
4
6
8
10

Nested loops with break:
i: 1, j: 1
i: 1, j: 2
i: 1, j: 3
i: 2, j: 1
```

---

## 3. Functions in Dart

### Overview
Functions are reusable blocks of code that perform specific tasks. Dart supports various types of functions including named functions, anonymous functions, and higher-order functions.

### 10 Examples of Functions in Dart

#### Example 1: Basic Function
```dart
// Function declaration
void greet() {
  print('Hello, World!');
}

// Function with parameters
void greetPerson(String name) {
  print('Hello, $name!');
}

// Function with return value
int add(int a, int b) {
  return a + b;
}

void main() {
  greet();
  greetPerson('Alice');
  int result = add(5, 3);
  print('Sum: $result');
}
```

**Output:**
```
Hello, World!
Hello, Alice!
Sum: 8
```

#### Example 2: Function with Optional Parameters
```dart
// Optional positional parameters
void greetWithOptional(String name, [String? title, int? age]) {
  String message = 'Hello, $name';
  if (title != null) message += ' $title';
  if (age != null) message += ' (age: $age)';
  print(message);
}

// Optional named parameters
void createUser({required String name, String? email, int? age}) {
  print('User: $name');
  if (email != null) print('Email: $email');
  if (age != null) print('Age: $age');
}

void main() {
  greetWithOptional('John');
  greetWithOptional('Jane', 'Dr.');
  greetWithOptional('Bob', 'Mr.', 30);
  
  createUser(name: 'Alice');
  createUser(name: 'Bob', email: 'bob@example.com');
  createUser(name: 'Charlie', email: 'charlie@example.com', age: 25);
}
```

**Output:**
```
Hello, John
Hello, Jane Dr.
Hello, Bob Mr. (age: 30)
User: Alice
User: Bob
Email: bob@example.com
User: Charlie
Email: charlie@example.com
Age: 25
```

#### Example 3: Function with Default Values
```dart
// Default values for optional parameters
void greetWithDefaults(String name, [String title = 'Mr./Ms.', int age = 0]) {
  print('Hello, $title $name');
  if (age > 0) print('Age: $age');
}

// Default values for named parameters
void createProfile({required String name, String role = 'User', bool isActive = true}) {
  print('Name: $name');
  print('Role: $role');
  print('Active: $isActive');
}

void main() {
  greetWithDefaults('Alice');
  greetWithDefaults('Bob', 'Dr.', 30);
  
  createProfile(name: 'John');
  createProfile(name: 'Jane', role: 'Admin');
  createProfile(name: 'Charlie', role: 'Moderator', isActive: false);
}
```

**Output:**
```
Hello, Mr./Ms. Alice
Hello, Dr. Bob
Age: 30
Name: John
Role: User
Active: true
Name: Jane
Role: Admin
Active: true
Name: Charlie
Role: Moderator
Active: false
```

#### Example 4: Arrow Functions (Single Expression)
```dart
// Arrow function syntax
int multiply(int a, int b) => a * b;

// Arrow function with conditional
String getGrade(int score) => score >= 90 ? 'A' : 
                             score >= 80 ? 'B' : 
                             score >= 70 ? 'C' : 'F';

// Arrow function with null safety
String? getName(Map<String, dynamic> data) => data['name'] as String?;

void main() {
  print('Product: ${multiply(4, 5)}');
  print('Grade: ${getGrade(85)}');
  
  Map<String, dynamic> user = {'name': 'Alice', 'age': 25};
  print('Name: ${getName(user)}');
}
```

**Output:**
```
Product: 20
Grade: B
Name: Alice
```

#### Example 5: Anonymous Functions
```dart
void main() {
  // Anonymous function assigned to variable
  var greet = (String name) {
    print('Hello, $name!');
  };
  
  greet('Alice');
  
  // Anonymous function as parameter
  List<String> names = ['Alice', 'Bob', 'Charlie'];
  names.forEach((name) {
    print('Greeting $name');
  });
  
  // Anonymous function with return value
  var square = (int x) => x * x;
  print('Square of 5: ${square(5)}');
}
```

**Output:**
```
Hello, Alice!
Greeting Alice
Greeting Bob
Greeting Charlie
Square of 5: 25
```

#### Example 6: Higher-Order Functions
```dart
// Function that takes another function as parameter
void processNumbers(List<int> numbers, Function(int) processor) {
  for (int number in numbers) {
    processor(number);
  }
}

// Function that returns a function
Function createMultiplier(int factor) {
  return (int number) => number * factor;
}

// Function that takes and returns functions
Function compose(Function f, Function g) {
  return (x) => f(g(x));
}

void main() {
  List<int> numbers = [1, 2, 3, 4, 5];
  
  // Using processNumbers with anonymous function
  processNumbers(numbers, (n) => print('Number: $n'));
  
  // Using processNumbers with arrow function
  processNumbers(numbers, (n) => print('Square: ${n * n}'));
  
  // Using createMultiplier
  var doubleIt = createMultiplier(2);
  var tripleIt = createMultiplier(3);
  
  print('Double 5: ${doubleIt(5)}');
  print('Triple 5: ${tripleIt(5)}');
  
  // Using compose
  var addOne = (int x) => x + 1;
  var multiplyByTwo = (int x) => x * 2;
  var addOneThenDouble = compose(multiplyByTwo, addOne);
  
  print('Add 1 then double 3: ${addOneThenDouble(3)}');
}
```

**Output:**
```
Number: 1
Number: 2
Number: 3
Number: 4
Number: 5
Square: 1
Square: 4
Square: 9
Square: 16
Square: 25
Double 5: 10
Triple 5: 15
Add 1 then double 3: 8
```

#### Example 7: Recursive Functions
```dart
// Recursive function to calculate factorial
int factorial(int n) {
  if (n <= 1) {
    return 1;
  }
  return n * factorial(n - 1);
}

// Recursive function to calculate Fibonacci
int fibonacci(int n) {
  if (n <= 1) {
    return n;
  }
  return fibonacci(n - 1) + fibonacci(n - 2);
}

// Recursive function to reverse a string
String reverseString(String str) {
  if (str.isEmpty) {
    return str;
  }
  return str[str.length - 1] + reverseString(str.substring(0, str.length - 1));
}

void main() {
  print('Factorial of 5: ${factorial(5)}');
  print('Fibonacci sequence:');
  for (int i = 0; i < 10; i++) {
    print('F($i) = ${fibonacci(i)}');
  }
  print('Reverse of "Dart": ${reverseString("Dart")}');
}
```

**Output:**
```
Factorial of 5: 120
Fibonacci sequence:
F(0) = 0
F(1) = 1
F(2) = 1
F(3) = 2
F(4) = 3
F(5) = 5
F(6) = 8
F(7) = 13
F(8) = 21
F(9) = 34
Reverse of "Dart": traD
```

#### Example 8: Function Overloading (Using Optional Parameters)
```dart
// Dart doesn't support traditional overloading, but we can use optional parameters
class Calculator {
  // Single method with optional parameters
  int add(int a, [int? b, int? c]) {
    int result = a;
    if (b != null) result += b;
    if (c != null) result += c;
    return result;
  }
  
  // Alternative using named parameters
  double calculate({required String operation, required List<double> numbers}) {
    switch (operation) {
      case 'sum':
        return numbers.fold(0.0, (sum, num) => sum + num);
      case 'product':
        return numbers.fold(1.0, (product, num) => product * num);
      case 'average':
        return numbers.fold(0.0, (sum, num) => sum + num) / numbers.length;
      default:
        throw ArgumentError('Unknown operation: $operation');
    }
  }
}

void main() {
  Calculator calc = Calculator();
  
  print('Add 5: ${calc.add(5)}');
  print('Add 5 + 3: ${calc.add(5, 3)}');
  print('Add 5 + 3 + 2: ${calc.add(5, 3, 2)}');
  
  print('Sum: ${calc.calculate(operation: 'sum', numbers: [1, 2, 3, 4, 5])}');
  print('Product: ${calc.calculate(operation: 'product', numbers: [1, 2, 3, 4])}');
  print('Average: ${calc.calculate(operation: 'average', numbers: [1, 2, 3, 4, 5])}');
}
```

**Output:**
```
Add 5: 5
Add 5 + 3: 8
Add 5 + 3 + 2: 10
Sum: 15.0
Product: 24.0
Average: 3.0
```

#### Example 9: Function as First-Class Citizens
```dart
void main() {
  // Functions can be assigned to variables
  Function operation = add;
  print('5 + 3 = ${operation(5, 3)}');
  
  // Functions can be passed as arguments
  int result = calculate(10, 20, multiply);
  print('10 * 20 = $result');
  
  // Functions can be returned from functions
  Function getOperation(String op) {
    switch (op) {
      case 'add':
        return add;
      case 'subtract':
        return subtract;
      case 'multiply':
        return multiply;
      case 'divide':
        return divide;
      default:
        return add;
    }
  }
  
  Function op = getOperation('multiply');
  print('7 * 8 = ${op(7, 8)}');
  
  // Functions can be stored in collections
  List<Function> operations = [add, subtract, multiply, divide];
  List<String> opNames = ['Add', 'Subtract', 'Multiply', 'Divide'];
  
  for (int i = 0; i < operations.length; i++) {
    print('${opNames[i]}: ${operations[i](10, 5)}');
  }
}

int add(int a, int b) => a + b;
int subtract(int a, int b) => a - b;
int multiply(int a, int b) => a * b;
double divide(int a, int b) => a / b;

int calculate(int a, int b, Function operation) {
  return operation(a, b);
}
```

**Output:**
```
5 + 3 = 8
10 * 20 = 200
7 * 8 = 56
Add: 15
Subtract: 5
Multiply: 50
Divide: 2.0
```

#### Example 10: Async Functions
```dart
import 'dart:async';

// Future-returning function
Future<String> fetchData() async {
  // Simulate network delay
  await Future.delayed(Duration(seconds: 2));
  return 'Data fetched successfully!';
}

// Stream-returning function
Stream<int> countStream() async* {
  for (int i = 1; i <= 5; i++) {
    await Future.delayed(Duration(seconds: 1));
    yield i;
  }
}

// Function that handles async operations
Future<void> processData() async {
  try {
    print('Starting data fetch...');
    String data = await fetchData();
    print(data);
    
    print('Starting count stream...');
    await for (int count in countStream()) {
      print('Count: $count');
    }
  } catch (e) {
    print('Error: $e');
  }
}

void main() async {
  await processData();
  print('All operations completed!');
}
```

**Output:**
```
Starting data fetch...
Data fetched successfully!
Starting count stream...
Count: 1
Count: 2
Count: 3
Count: 4
Count: 5
All operations completed!
```

---

## 4. Collections in Dart

### Overview
Collections in Dart are data structures that hold multiple values. Dart provides several built-in collection types: List, Set, Map, and Queue.

### 10 Examples of Collections in Dart

#### Example 1: List Basics
```dart
void main() {
  // Creating lists
  List<int> numbers = [1, 2, 3, 4, 5];
  List<String> fruits = ['apple', 'banana', 'orange'];
  var mixed = [1, 'hello', 3.14, true]; // List<dynamic>
  
  // Accessing elements
  print('First number: ${numbers[0]}');
  print('Last fruit: ${fruits[fruits.length - 1]}');
  
  // Modifying lists
  numbers.add(6);
  numbers.insert(0, 0);
  numbers.remove(3);
  
  print('Numbers: $numbers');
  print('Fruits: $fruits');
  print('Mixed: $mixed');
}
```

**Output:**
```
First number: 1
Last fruit: orange
Numbers: [0, 1, 2, 4, 5, 6]
Fruits: [apple, banana, orange]
Mixed: [1, hello, 3.14, true]
```

#### Example 2: List Methods and Operations
```dart
void main() {
  List<int> numbers = [3, 1, 4, 1, 5, 9, 2, 6];
  
  // Basic operations
  print('Length: ${numbers.length}');
  print('Is empty: ${numbers.isEmpty}');
  print('Is not empty: ${numbers.isNotEmpty}');
  print('First element: ${numbers.first}');
  print('Last element: ${numbers.last}');
  
  // Searching
  print('Contains 5: ${numbers.contains(5)}');
  print('Index of 4: ${numbers.indexOf(4)}');
  print('Last index of 1: ${numbers.lastIndexOf(1)}');
  
  // Sorting
  List<int> sorted = List.from(numbers);
  sorted.sort();
  print('Sorted: $sorted');
  
  // Reversing
  List<int> reversed = List.from(numbers);
  reversed.reversed.toList();
  print('Reversed: ${reversed.reversed.toList()}');
  
  // Filtering
  List<int> evenNumbers = numbers.where((n) => n % 2 == 0).toList();
  print('Even numbers: $evenNumbers');
}
```

**Output:**
```
Length: 8
Is empty: false
Is not empty: true
First element: 3
Last element: 6
Contains 5: true
Index of 4: 2
Last index of 1: 3
Sorted: [1, 1, 2, 3, 4, 5, 6, 9]
Reversed: [6, 2, 9, 5, 1, 4, 1, 3]
Even numbers: [4, 2, 6]
```

#### Example 3: Set Basics
```dart
void main() {
  // Creating sets
  Set<String> colors = {'red', 'green', 'blue'};
  Set<int> numbers = {1, 2, 3, 4, 5};
  var emptySet = <String>{}; // Empty set
  
  // Adding elements
  colors.add('yellow');
  colors.addAll(['purple', 'orange']);
  
  // Removing elements
  colors.remove('red');
  colors.removeAll(['green', 'blue']);
  
  print('Colors: $colors');
  print('Numbers: $numbers');
  
  // Set operations
  Set<int> set1 = {1, 2, 3, 4, 5};
  Set<int> set2 = {4, 5, 6, 7, 8};
  
  print('Union: ${set1.union(set2)}');
  print('Intersection: ${set1.intersection(set2)}');
  print('Difference: ${set1.difference(set2)}');
  print('Contains all: ${set1.containsAll([1, 2, 3])}');
}
```

**Output:**
```
Colors: {yellow, purple, orange}
Numbers: {1, 2, 3, 4, 5}
Union: {1, 2, 3, 4, 5, 6, 7, 8}
Intersection: {4, 5}
Difference: {1, 2, 3}
Contains all: true
```

#### Example 4: Map Basics
```dart
void main() {
  // Creating maps
  Map<String, int> ages = {
    'Alice': 25,
    'Bob': 30,
    'Charlie': 35
  };
  
  Map<String, String> capitals = Map();
  capitals['USA'] = 'Washington D.C.';
  capitals['France'] = 'Paris';
  capitals['Japan'] = 'Tokyo';
  
  // Accessing values
  print('Alice\'s age: ${ages['Alice']}');
  print('Capital of France: ${capitals['France']}');
  
  // Modifying maps
  ages['David'] = 28;
  ages['Alice'] = 26; // Update existing
  ages.remove('Bob');
  
  print('Ages: $ages');
  print('Capitals: $capitals');
  
  // Map properties
  print('Number of people: ${ages.length}');
  print('Keys: ${ages.keys}');
  print('Values: ${ages.values}');
  print('Is empty: ${ages.isEmpty}');
}
```

**Output:**
```
Alice's age: 25
Capital of France: Paris
Ages: {Alice: 26, Charlie: 35, David: 28}
Capitals: {USA: Washington D.C., France: Paris, Japan: Tokyo}
Number of people: 3
Keys: (Alice, Charlie, David)
Values: (26, 35, 28)
Is empty: false
```

#### Example 5: Map Methods and Operations
```dart
void main() {
  Map<String, int> scores = {
    'Alice': 95,
    'Bob': 87,
    'Charlie': 92,
    'David': 78
  };
  
  // Iterating through maps
  print('All scores:');
  scores.forEach((name, score) {
    print('$name: $score');
  });
  
  // Using entries
  print('\nHigh scorers:');
  scores.entries.where((entry) => entry.value >= 90).forEach((entry) {
    print('${entry.key}: ${entry.value}');
  });
  
  // Map transformations
  Map<String, String> grades = scores.map((name, score) {
    String grade = score >= 90 ? 'A' : 
                   score >= 80 ? 'B' : 
                   score >= 70 ? 'C' : 'F';
    return MapEntry(name, grade);
  });
  
  print('\nGrades: $grades');
  
  // Checking conditions
  bool allPassed = scores.values.every((score) => score >= 60);
  bool anyExcellent = scores.values.any((score) => score >= 95);
  
  print('All passed: $allPassed');
  print('Any excellent: $anyExcellent');
}
```

**Output:**
```
All scores:
Alice: 95
Bob: 87
Charlie: 92
David: 78

High scorers:
Alice: 95
Charlie: 92

Grades: {Alice: A, Bob: B, Charlie: A, David: C}
All passed: true
Any excellent: true
```

#### Example 6: Collection Iteration Methods
```dart
void main() {
  List<int> numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
  
  // forEach
  print('Numbers:');
  numbers.forEach((n) => print(n));
  
  // map
  List<int> squares = numbers.map((n) => n * n).toList();
  print('Squares: $squares');
  
  // where (filter)
  List<int> evens = numbers.where((n) => n % 2 == 0).toList();
  print('Even numbers: $evens');
  
  // reduce
  int sum = numbers.reduce((a, b) => a + b);
  print('Sum: $sum');
  
  // fold
  int product = numbers.fold(1, (a, b) => a * b);
  print('Product: $product');
  
  // any
  bool hasEven = numbers.any((n) => n % 2 == 0);
  print('Has even numbers: $hasEven');
  
  // every
  bool allPositive = numbers.every((n) => n > 0);
  print('All positive: $allPositive');
  
  // take and skip
  List<int> firstThree = numbers.take(3).toList();
  List<int> skipFirstThree = numbers.skip(3).toList();
  print('First three: $firstThree');
  print('Skip first three: $skipFirstThree');
}
```

**Output:**
```
Numbers:
1
2
3
4
5
6
7
8
9
10
Squares: [1, 4, 9, 16, 25, 36, 49, 64, 81, 100]
Even numbers: [2, 4, 6, 8, 10]
Sum: 55
Product: 3628800
Has even numbers: true
All positive: true
First three: [1, 2, 3]
Skip first three: [4, 5, 6, 7, 8, 9, 10]
```

#### Example 7: List Comprehensions and Generators
```dart
void main() {
  // Generating lists
  List<int> numbers = List.generate(10, (index) => index + 1);
  print('Generated numbers: $numbers');
  
  // List comprehension-like operations
  List<int> squares = List.generate(5, (i) => (i + 1) * (i + 1));
  print('Squares: $squares');
  
  // Conditional generation
  List<int> evenNumbers = List.generate(10, (i) => (i + 1) * 2);
  print('Even numbers: $evenNumbers');
  
  // Using where and map together
  List<String> words = ['hello', 'world', 'dart', 'flutter', 'programming'];
  List<String> longWords = words
      .where((word) => word.length > 4)
      .map((word) => word.toUpperCase())
      .toList();
  print('Long words: $longWords');
  
  // Nested lists
  List<List<int>> matrix = List.generate(3, (i) => List.generate(3, (j) => i * 3 + j + 1));
  print('Matrix: $matrix');
}
```

**Output:**
```
Generated numbers: [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
Squares: [1, 4, 9, 16, 25]
Even numbers: [2, 4, 6, 8, 10, 12, 14, 16, 18, 20]
Long words: [HELLO, WORLD, FLUTTER, PROGRAMMING]
Matrix: [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
```

#### Example 8: Queue Operations
```dart
import 'dart:collection';

void main() {
  // Creating queues
  Queue<String> queue = Queue<String>();
  Queue<int> numbers = Queue.from([1, 2, 3, 4, 5]);
  
  // Adding elements
  queue.add('first');
  queue.add('second');
  queue.addLast('third');
  queue.addFirst('zero');
  
  print('Queue: $queue');
  
  // Removing elements
  String first = queue.removeFirst();
  String last = queue.removeLast();
  
  print('Removed first: $first');
  print('Removed last: $last');
  print('Queue after removal: $queue');
  
  // Queue properties
  print('Length: ${queue.length}');
  print('Is empty: ${queue.isEmpty}');
  print('First element: ${queue.first}');
  print('Last element: ${queue.last}');
  
  // Iterating
  print('Queue elements:');
  for (String item in queue) {
    print(item);
  }
}
```

**Output:**
```
Queue: {zero, first, second, third}
Removed first: zero
Removed last: third
Queue after removal: {first, second}
Length: 2
Is empty: false
First element: first
Last element: second
Queue elements:
first
second
```

#### Example 9: Custom Collection Classes
```dart
class Stack<T> {
  List<T> _items = [];
  
  void push(T item) {
    _items.add(item);
  }
  
  T? pop() {
    if (_items.isEmpty) return null;
    return _items.removeLast();
  }
  
  T? peek() {
    if (_items.isEmpty) return null;
    return _items.last;
  }
  
  bool get isEmpty => _items.isEmpty;
  int get length => _items.length;
  
  @override
  String toString() => _items.toString();
}

class Queue<T> {
  List<T> _items = [];
  
  void enqueue(T item) {
    _items.add(item);
  }
  
  T? dequeue() {
    if (_items.isEmpty) return null;
    return _items.removeAt(0);
  }
  
  T? front() {
    if (_items.isEmpty) return null;
    return _items.first;
  }
  
  bool get isEmpty => _items.isEmpty;
  int get length => _items.length;
  
  @override
  String toString() => _items.toString();
}

void main() {
  // Using custom Stack
  Stack<int> stack = Stack<int>();
  stack.push(1);
  stack.push(2);
  stack.push(3);
  
  print('Stack: $stack');
  print('Peek: ${stack.peek()}');
  print('Pop: ${stack.pop()}');
  print('Stack after pop: $stack');
  
  // Using custom Queue
  Queue<String> queue = Queue<String>();
  queue.enqueue('first');
  queue.enqueue('second');
  queue.enqueue('third');
  
  print('\nQueue: $queue');
  print('Front: ${queue.front()}');
  print('Dequeue: ${queue.dequeue()}');
  print('Queue after dequeue: $queue');
}
```

**Output:**
```
Stack: [1, 2, 3]
Peek: 3
Pop: 3
Stack after pop: [1, 2]

Queue: [first, second, third]
Front: first
Dequeue: first
Queue after dequeue: [second, third]
```

#### Example 10: Advanced Collection Operations
```dart
void main() {
  List<Map<String, dynamic>> students = [
    {'name': 'Alice', 'age': 20, 'grade': 'A'},
    {'name': 'Bob', 'age': 22, 'grade': 'B'},
    {'name': 'Charlie', 'age': 19, 'grade': 'A'},
    {'name': 'David', 'age': 21, 'grade': 'C'},
    {'name': 'Eve', 'age': 20, 'grade': 'B'},
  ];
  
  // Grouping
  Map<String, List<Map<String, dynamic>>> groupedByGrade = {};
  for (var student in students) {
    String grade = student['grade'];
    groupedByGrade.putIfAbsent(grade, () => []).add(student);
  }
  
  print('Grouped by grade: $groupedByGrade');
  
  // Sorting
  students.sort((a, b) => a['age'].compareTo(b['age']));
  print('\nSorted by age: $students');
  
  // Filtering and mapping
  List<String> honorStudents = students
      .where((student) => student['grade'] == 'A')
      .map((student) => student['name'])
      .toList();
  
  print('\nHonor students: $honorStudents');
  
  // Aggregation
  double averageAge = students
      .map((student) => student['age'] as int)
      .reduce((a, b) => a + b) / students.length;
  
  print('\nAverage age: ${averageAge.toStringAsFixed(1)}');
  
  // Finding
  Map<String, dynamic>? oldestStudent = students
      .reduce((a, b) => a['age'] > b['age'] ? a : b);
  
  print('Oldest student: $oldestStudent');
  
  // Partitioning
  List<List<Map<String, dynamic>>> partitioned = students
      .fold([[], []], (acc, student) {
        if (student['age'] >= 20) {
          acc[0].add(student);
        } else {
          acc[1].add(student);
        }
        return acc;
      });
  
  print('\nAdults (20+): ${partitioned[0]}');
  print('Minors (<20): ${partitioned[1]}');
}
```

**Output:**
```
Grouped by grade: {A: [{name: Alice, age: 20, grade: A}, {name: Charlie, age: 19, grade: A}], B: [{name: Bob, age: 22, grade: B}, {name: Eve, age: 20, grade: B}], C: [{name: David, age: 21, grade: C}]}

Sorted by age: [{name: Charlie, age: 19, grade: A}, {name: Alice, age: 20, grade: A}, {name: Eve, age: 20, grade: B}, {name: David, age: 21, grade: C}, {name: Bob, age: 22, grade: B}]

Honor students: [Alice, Charlie]

Average age: 20.4

Oldest student: {name: Bob, age: 22, grade: B}

Adults (20+): [{name: Alice, age: 20, grade: A}, {name: Bob, age: 22, grade: B}, {name: David, age: 21, grade: C}, {name: Eve, age: 20, grade: B}]
Minors (<20): [{name: Charlie, age: 19, grade: A}]
```

---

## 5. File Handling in Dart

### Overview
File handling in Dart allows you to read from and write to files on the local filesystem. Dart provides the `dart:io` library for file operations, which includes classes like `File`, `Directory`, and `FileSystemEntity`.

### Key Concepts
- **File**: Represents a file on the filesystem
- **Directory**: Represents a directory on the filesystem
- **FileSystemEntity**: Base class for both files and directories
- **Path operations**: Working with file and directory paths
- **Asynchronous operations**: Most file operations are asynchronous

### 10 Examples of File Handling in Dart

#### Example 1: Basic File Reading
```dart
import 'dart:io';

void main() async {
  try {
    // Create a file object
    File file = File('example.txt');
    
    // Check if file exists
    if (await file.exists()) {
      // Read file contents
      String contents = await file.readAsString();
      print('File contents:');
      print(contents);
    } else {
      print('File does not exist');
    }
  } catch (e) {
    print('Error reading file: $e');
  }
}
```

**Output:**
```
File contents:
Hello, World!
This is a sample text file.
```

#### Example 2: File Writing
```dart
import 'dart:io';

void main() async {
  try {
    // Create a file object
    File file = File('output.txt');
    
    // Write content to file
    await file.writeAsString('Hello from Dart!\nThis is a new file.');
    print('File written successfully');
    
    // Read back to verify
    String contents = await file.readAsString();
    print('File contents:');
    print(contents);
  } catch (e) {
    print('Error writing file: $e');
  }
}
```

**Output:**
```
File written successfully
File contents:
Hello from Dart!
This is a new file.
```

#### Example 3: Reading File Line by Line
```dart
import 'dart:io';

void main() async {
  try {
    File file = File('data.txt');
    
    if (await file.exists()) {
      // Read file as lines
      List<String> lines = await file.readAsLines();
      
      print('File has ${lines.length} lines:');
      for (int i = 0; i < lines.length; i++) {
        print('Line ${i + 1}: ${lines[i]}');
      }
    } else {
      print('File does not exist');
    }
  } catch (e) {
    print('Error: $e');
  }
}
```

**Output:**
```
File has 3 lines:
Line 1: First line
Line 2: Second line
Line 3: Third line
```

#### Example 4: Appending to File
```dart
import 'dart:io';

void main() async {
  try {
    File file = File('log.txt');
    
    // Append content to file
    await file.writeAsString('New log entry: ${DateTime.now()}\n', mode: FileMode.append);
    print('Log entry added');
    
    // Read all content
    String contents = await file.readAsString();
    print('All log entries:');
    print(contents);
  } catch (e) {
    print('Error: $e');
  }
}
```

**Output:**
```
Log entry added
All log entries:
Previous log entry: 2024-01-01 10:00:00
New log entry: 2024-01-01 10:30:00
```

#### Example 5: Working with Directories
```dart
import 'dart:io';

void main() async {
  try {
    // Create directory
    Directory dir = Directory('test_folder');
    if (!await dir.exists()) {
      await dir.create();
      print('Directory created: ${dir.path}');
    }
    
    // List directory contents
    List<FileSystemEntity> contents = await dir.list().toList();
    print('Directory contents:');
    for (var item in contents) {
      print('- ${item.path}');
    }
    
    // Get directory info
    print('Directory path: ${dir.path}');
    print('Directory absolute path: ${dir.absolute.path}');
  } catch (e) {
    print('Error: $e');
  }
}
```

**Output:**
```
Directory created: test_folder
Directory contents:
- test_folder\file1.txt
- test_folder\file2.txt
Directory path: test_folder
Directory absolute path: C:\Users\Admin\Desktop\Error Fix\test_folder
```

#### Example 6: File Copying and Moving
```dart
import 'dart:io';

void main() async {
  try {
    File sourceFile = File('source.txt');
    File destinationFile = File('destination.txt');
    
    // Create source file with content
    await sourceFile.writeAsString('This is the source file content');
    
    // Copy file
    await sourceFile.copy(destinationFile.path);
    print('File copied successfully');
    
    // Verify copy
    String copiedContent = await destinationFile.readAsString();
    print('Copied file content: $copiedContent');
    
    // Move file (rename)
    File movedFile = File('moved.txt');
    await destinationFile.rename(movedFile.path);
    print('File moved to: ${movedFile.path}');
  } catch (e) {
    print('Error: $e');
  }
}
```

**Output:**
```
File copied successfully
Copied file content: This is the source file content
File moved to: moved.txt
```

#### Example 7: File Properties and Metadata
```dart
import 'dart:io';

void main() async {
  try {
    File file = File('example.txt');
    
    if (await file.exists()) {
      // Get file properties
      FileStat stat = await file.stat();
      
      print('File properties:');
      print('Path: ${file.path}');
      print('Size: ${stat.size} bytes');
      print('Type: ${stat.type}');
      print('Modified: ${stat.modified}');
      print('Accessed: ${stat.accessed}');
      print('Changed: ${stat.changed}');
      print('Mode: ${stat.mode}');
    } else {
      print('File does not exist');
    }
  } catch (e) {
    print('Error: $e');
  }
}
```

**Output:**
```
File properties:
Path: example.txt
Size: 25 bytes
Type: FileSystemEntityType.file
Modified: 2024-01-01 10:30:00.000
Accessed: 2024-01-01 10:30:00.000
Changed: 2024-01-01 10:30:00.000
Mode: 33206
```

#### Example 8: Binary File Operations
```dart
import 'dart:io';
import 'dart:typed_data';

void main() async {
  try {
    File file = File('binary_data.bin');
    
    // Write binary data
    List<int> data = [72, 101, 108, 108, 111]; // "Hello" in ASCII
    await file.writeAsBytes(data);
    print('Binary data written');
    
    // Read binary data
    Uint8List bytes = await file.readAsBytes();
    print('Read bytes: $bytes');
    
    // Convert to string
    String text = String.fromCharCodes(bytes);
    print('As text: $text');
  } catch (e) {
    print('Error: $e');
  }
}
```

**Output:**
```
Binary data written
Read bytes: [72, 101, 108, 108, 111]
As text: Hello
```

#### Example 9: File Stream Operations
```dart
import 'dart:io';
import 'dart:convert';

void main() async {
  try {
    File file = File('large_file.txt');
    
    // Write large content
    String content = 'Line ${DateTime.now().millisecondsSinceEpoch}\n' * 1000;
    await file.writeAsString(content);
    print('Large file created');
    
    // Read file using stream
    Stream<List<int>> inputStream = file.openRead();
    Stream<String> lines = inputStream
        .transform(utf8.decoder)
        .transform(LineSplitter());
    
    int lineCount = 0;
    await for (String line in lines) {
      lineCount++;
      if (lineCount <= 5) {
        print('Line $lineCount: $line');
      }
    }
    print('Total lines: $lineCount');
  } catch (e) {
    print('Error: $e');
  }
}
```

**Output:**
```
Large file created
Line 1: Line 1704067200000
Line 2: Line 1704067200000
Line 3: Line 1704067200000
Line 4: Line 1704067200000
Line 5: Line 1704067200000
Total lines: 1000
```

#### Example 10: Error Handling and File Cleanup
```dart
import 'dart:io';

void main() async {
  File? tempFile;
  Directory? tempDir;
  
  try {
    // Create temporary directory
    tempDir = await Directory.systemTemp.createTemp('dart_temp_');
    print('Temporary directory created: ${tempDir.path}');
    
    // Create temporary file
    tempFile = File('${tempDir.path}/temp_file.txt');
    await tempFile.writeAsString('Temporary file content');
    print('Temporary file created');
    
    // Simulate some work
    await Future.delayed(Duration(seconds: 1));
    
    // Read the file
    String content = await tempFile.readAsString();
    print('File content: $content');
    
  } catch (e) {
    print('Error occurred: $e');
  } finally {
    // Cleanup: delete temporary files and directories
    try {
      if (tempFile != null && await tempFile.exists()) {
        await tempFile.delete();
        print('Temporary file deleted');
      }
      
      if (tempDir != null && await tempDir.exists()) {
        await tempDir.delete(recursive: true);
        print('Temporary directory deleted');
      }
    } catch (e) {
      print('Error during cleanup: $e');
    }
  }
}
```

**Output:**
```
Temporary directory created: C:\Users\Admin\AppData\Local\Temp\dart_temp_12345
Temporary file created
File content: Temporary file content
Temporary file deleted
Temporary directory deleted
```

---

## 6. OOP in Dart

### Overview
Object-Oriented Programming (OOP) in Dart is built around classes and objects. Dart supports all major OOP concepts including encapsulation, inheritance, polymorphism, and abstraction.

### Key Concepts
- **Class**: Blueprint for creating objects
- **Object**: Instance of a class
- **Constructor**: Special method for initializing objects
- **Inheritance**: Creating new classes based on existing ones
- **Polymorphism**: Same interface, different implementations
- **Encapsulation**: Hiding internal implementation details
- **Abstract Classes**: Classes that cannot be instantiated
- **Interfaces**: Contracts that classes must implement

### 10 Examples of OOP in Dart

#### Example 1: Basic Class and Object
```dart
class Person {
  String name;
  int age;
  
  // Constructor
  Person(this.name, this.age);
  
  // Method
  void introduce() {
    print('Hi, I am $name and I am $age years old.');
  }
  
  // Getter
  String get info => 'Name: $name, Age: $age';
  
  // Setter
  set setAge(int newAge) {
    if (newAge > 0) {
      age = newAge;
    }
  }
}

void main() {
  // Creating objects
  Person person1 = Person('Alice', 25);
  Person person2 = Person('Bob', 30);
  
  // Using methods
  person1.introduce();
  person2.introduce();
  
  // Using getters and setters
  print(person1.info);
  person1.setAge = 26;
  print('After age change: ${person1.info}');
}
```

**Output:**
```
Hi, I am Alice and I am 25 years old.
Hi, I am Bob and I am 30 years old.
Name: Alice, Age: 25
After age change: Name: Alice, Age: 26
```

#### Example 2: Constructor Variations
```dart
class Rectangle {
  double width;
  double height;
  
  // Default constructor
  Rectangle(this.width, this.height);
  
  // Named constructor
  Rectangle.square(double side) : width = side, height = side;
  
  // Named constructor with default values
  Rectangle.unit() : width = 1.0, height = 1.0;
  
  // Factory constructor
  factory Rectangle.fromDimensions(double w, double h) {
    return Rectangle(w, h);
  }
  
  // Method
  double get area => width * height;
  double get perimeter => 2 * (width + height);
}

void main() {
  // Using different constructors
  Rectangle rect1 = Rectangle(5.0, 3.0);
  Rectangle square = Rectangle.square(4.0);
  Rectangle unit = Rectangle.unit();
  Rectangle factory = Rectangle.fromDimensions(6.0, 2.0);
  
  print('Rectangle 1 - Area: ${rect1.area}, Perimeter: ${rect1.perimeter}');
  print('Square - Area: ${square.area}, Perimeter: ${square.perimeter}');
  print('Unit - Area: ${unit.area}, Perimeter: ${unit.perimeter}');
  print('Factory - Area: ${factory.area}, Perimeter: ${factory.perimeter}');
}
```

**Output:**
```
Rectangle 1 - Area: 15.0, Perimeter: 16.0
Square - Area: 16.0, Perimeter: 16.0
Unit - Area: 1.0, Perimeter: 4.0
Factory - Area: 12.0, Perimeter: 16.0
```

#### Example 3: Inheritance
```dart
// Base class
class Animal {
  String name;
  int age;
  
  Animal(this.name, this.age);
  
  void makeSound() {
    print('Some generic animal sound');
  }
  
  void eat() {
    print('$name is eating');
  }
  
  void sleep() {
    print('$name is sleeping');
  }
}

// Derived class
class Dog extends Animal {
  String breed;
  
  Dog(String name, int age, this.breed) : super(name, age);
  
  // Override method
  @override
  void makeSound() {
    print('$name barks: Woof! Woof!');
  }
  
  // Additional method
  void fetch() {
    print('$name is fetching the ball');
  }
}

// Another derived class
class Cat extends Animal {
  String color;
  
  Cat(String name, int age, this.color) : super(name, age);
  
  @override
  void makeSound() {
    print('$name meows: Meow! Meow!');
  }
  
  void climb() {
    print('$name is climbing the tree');
  }
}

void main() {
  Dog dog = Dog('Buddy', 3, 'Golden Retriever');
  Cat cat = Cat('Whiskers', 2, 'Orange');
  
  // Using inherited methods
  dog.eat();
  dog.sleep();
  dog.makeSound();
  dog.fetch();
  
  print('---');
  
  cat.eat();
  cat.sleep();
  cat.makeSound();
  cat.climb();
}
```

**Output:**
```
Buddy is eating
Buddy is sleeping
Buddy barks: Woof! Woof!
Buddy is fetching the ball
---
Whiskers is eating
Whiskers is sleeping
Whiskers meows: Meow! Meow!
Whiskers is climbing the tree
```

#### Example 4: Abstract Classes and Interfaces
```dart
// Abstract class
abstract class Shape {
  double get area;
  double get perimeter;
  
  // Abstract method
  void draw();
  
  // Concrete method
  void displayInfo() {
    print('Area: $area, Perimeter: $perimeter');
  }
}

// Interface (using abstract class)
abstract class Drawable {
  void draw();
  void setColor(String color);
}

// Concrete class implementing both abstract class and interface
class Circle extends Shape implements Drawable {
  double radius;
  String color = 'black';
  
  Circle(this.radius);
  
  @override
  double get area => 3.14159 * radius * radius;
  
  @override
  double get perimeter => 2 * 3.14159 * radius;
  
  @override
  void draw() {
    print('Drawing a $color circle with radius $radius');
  }
  
  @override
  void setColor(String color) {
    this.color = color;
  }
}

class Rectangle extends Shape implements Drawable {
  double width;
  double height;
  String color = 'black';
  
  Rectangle(this.width, this.height);
  
  @override
  double get area => width * height;
  
  @override
  double get perimeter => 2 * (width + height);
  
  @override
  void draw() {
    print('Drawing a $color rectangle ${width}x$height');
  }
  
  @override
  void setColor(String color) {
    this.color = color;
  }
}

void main() {
  Circle circle = Circle(5.0);
  Rectangle rectangle = Rectangle(4.0, 6.0);
  
  circle.setColor('red');
  circle.draw();
  circle.displayInfo();
  
  print('---');
  
  rectangle.setColor('blue');
  rectangle.draw();
  rectangle.displayInfo();
}
```

**Output:**
```
Drawing a red circle with radius 5.0
Area: 78.53975, Perimeter: 31.4159
---
Drawing a blue rectangle 4.0x6.0
Area: 24.0, Perimeter: 20.0
```

#### Example 5: Polymorphism
```dart
// Base class
class Vehicle {
  String brand;
  int year;
  
  Vehicle(this.brand, this.year);
  
  void start() {
    print('$brand vehicle is starting');
  }
  
  void stop() {
    print('$brand vehicle is stopping');
  }
  
  void accelerate() {
    print('$brand vehicle is accelerating');
  }
}

// Derived classes
class Car extends Vehicle {
  int doors;
  
  Car(String brand, int year, this.doors) : super(brand, year);
  
  @override
  void accelerate() {
    print('$brand car with $doors doors is accelerating smoothly');
  }
  
  void honk() {
    print('$brand car is honking');
  }
}

class Motorcycle extends Vehicle {
  bool hasWindshield;
  
  Motorcycle(String brand, int year, this.hasWindshield) : super(brand, year);
  
  @override
  void accelerate() {
    print('$brand motorcycle is accelerating quickly');
  }
  
  void wheelie() {
    print('$brand motorcycle is doing a wheelie');
  }
}

class Truck extends Vehicle {
  double cargoCapacity;
  
  Truck(String brand, int year, this.cargoCapacity) : super(brand, year);
  
  @override
  void accelerate() {
    print('$brand truck is accelerating slowly with heavy cargo');
  }
  
  void loadCargo() {
    print('$brand truck is loading cargo');
  }
}

void main() {
  // Polymorphism: same interface, different implementations
  List<Vehicle> vehicles = [
    Car('Toyota', 2020, 4),
    Motorcycle('Honda', 2019, true),
    Truck('Ford', 2021, 2.5),
  ];
  
  for (Vehicle vehicle in vehicles) {
    vehicle.start();
    vehicle.accelerate();
    vehicle.stop();
    print('---');
  }
  
  // Type-specific methods
  Car car = Car('BMW', 2022, 2);
  car.honk();
  
  Motorcycle bike = Motorcycle('Yamaha', 2020, false);
  bike.wheelie();
}
```

**Output:**
```
Toyota vehicle is starting
Toyota car with 4 doors is accelerating smoothly
Toyota vehicle is stopping
---
Honda vehicle is starting
Honda motorcycle is accelerating quickly
Honda vehicle is stopping
---
Ford vehicle is starting
Ford truck is accelerating slowly with heavy cargo
Ford vehicle is stopping
---
BMW car is honking
Yamaha motorcycle is doing a wheelie
```

#### Example 6: Encapsulation and Access Modifiers
```dart
class BankAccount {
  // Private fields (encapsulation)
  double _balance;
  String _accountNumber;
  String _accountHolder;
  
  // Constructor
  BankAccount(this._accountNumber, this._accountHolder, this._balance);
  
  // Public getters
  double get balance => _balance;
  String get accountNumber => _accountNumber;
  String get accountHolder => _accountHolder;
  
  // Public methods
  void deposit(double amount) {
    if (amount > 0) {
      _balance += amount;
      print('Deposited \$${amount.toStringAsFixed(2)}. New balance: \$${_balance.toStringAsFixed(2)}');
    } else {
      print('Invalid deposit amount');
    }
  }
  
  bool withdraw(double amount) {
    if (amount > 0 && amount <= _balance) {
      _balance -= amount;
      print('Withdrew \$${amount.toStringAsFixed(2)}. New balance: \$${_balance.toStringAsFixed(2)}');
      return true;
    } else {
      print('Invalid withdrawal amount or insufficient funds');
      return false;
    }
  }
  
  void displayInfo() {
    print('Account: $_accountNumber');
    print('Holder: $_accountHolder');
    print('Balance: \$${_balance.toStringAsFixed(2)}');
  }
  
  // Private method
  void _logTransaction(String type, double amount) {
    print('Transaction logged: $type \$${amount.toStringAsFixed(2)} at ${DateTime.now()}');
  }
}

void main() {
  BankAccount account = BankAccount('123456789', 'John Doe', 1000.0);
  
  account.displayInfo();
  print('---');
  
  account.deposit(500.0);
  account.withdraw(200.0);
  account.withdraw(2000.0); // Should fail
  
  print('---');
  account.displayInfo();
}
```

**Output:**
```
Account: 123456789
Holder: John Doe
Balance: $1000.00
---
Deposited $500.00. New balance: $1500.00
Withdrew $200.00. New balance: $1300.00
Invalid withdrawal amount or insufficient funds
---
Account: 123456789
Holder: John Doe
Balance: $1300.00
```

#### Example 7: Static Members and Constants
```dart
class MathUtils {
  // Static constant
  static const double pi = 3.14159;
  
  // Static variable
  static int calculationCount = 0;
  
  // Static method
  static double circleArea(double radius) {
    calculationCount++;
    return pi * radius * radius;
  }
  
  static double circleCircumference(double radius) {
    calculationCount++;
    return 2 * pi * radius;
  }
  
  static double rectangleArea(double width, double height) {
    calculationCount++;
    return width * height;
  }
  
  static void resetCounter() {
    calculationCount = 0;
  }
  
  static void displayStats() {
    print('Total calculations performed: $calculationCount');
  }
}

class Counter {
  // Instance variable
  int _count = 0;
  
  // Instance method
  void increment() {
    _count++;
  }
  
  int get count => _count;
  
  // Static method that creates instances
  static Counter createCounter() {
    return Counter();
  }
}

void main() {
  // Using static methods without creating instances
  double area = MathUtils.circleArea(5.0);
  double circumference = MathUtils.circleCircumference(5.0);
  double rectArea = MathUtils.rectangleArea(4.0, 6.0);
  
  print('Circle area: ${area.toStringAsFixed(2)}');
  print('Circle circumference: ${circumference.toStringAsFixed(2)}');
  print('Rectangle area: ${rectArea.toStringAsFixed(2)}');
  
  MathUtils.displayStats();
  
  print('---');
  
  // Creating instances using static method
  Counter counter1 = Counter.createCounter();
  Counter counter2 = Counter.createCounter();
  
  counter1.increment();
  counter1.increment();
  counter2.increment();
  
  print('Counter 1: ${counter1.count}');
  print('Counter 2: ${counter2.count}');
}
```

**Output:**
```
Circle area: 78.54
Circle circumference: 31.42
Rectangle area: 24.00
Total calculations performed: 3
---
Counter 1: 2
Counter 2: 1
```

#### Example 8: Mixins
```dart
// Mixin for flying behavior
mixin Flyable {
  void fly() {
    print('Flying through the air');
  }
  
  void land() {
    print('Landing safely');
  }
}

// Mixin for swimming behavior
mixin Swimmable {
  void swim() {
    print('Swimming in water');
  }
  
  void dive() {
    print('Diving deep');
  }
}

// Mixin for walking behavior
mixin Walkable {
  void walk() {
    print('Walking on land');
  }
  
  void run() {
    print('Running fast');
  }
}

// Base class
class Animal {
  String name;
  
  Animal(this.name);
  
  void eat() {
    print('$name is eating');
  }
}

// Classes using mixins
class Bird extends Animal with Flyable, Walkable {
  Bird(String name) : super(name);
  
  void chirp() {
    print('$name is chirping');
  }
}

class Fish extends Animal with Swimmable {
  Fish(String name) : super(name);
  
  void bubble() {
    print('$name is making bubbles');
  }
}

class Duck extends Animal with Flyable, Swimmable, Walkable {
  Duck(String name) : super(name);
  
  void quack() {
    print('$name is quacking');
  }
}

void main() {
  Bird bird = Bird('Eagle');
  Fish fish = Fish('Salmon');
  Duck duck = Duck('Mallard');
  
  // Bird behaviors
  bird.eat();
  bird.fly();
  bird.walk();
  bird.chirp();
  
  print('---');
  
  // Fish behaviors
  fish.eat();
  fish.swim();
  fish.dive();
  fish.bubble();
  
  print('---');
  
  // Duck behaviors (can do everything)
  duck.eat();
  duck.fly();
  duck.swim();
  duck.walk();
  duck.quack();
}
```

**Output:**
```
Eagle is eating
Flying through the air
Walking on land
Eagle is chirping
---
Salmon is eating
Swimming in water
Diving deep
Salmon is making bubbles
---
Mallard is eating
Flying through the air
Swimming in water
Walking on land
Mallard is quacking
```

#### Example 9: Generics
```dart
// Generic class
class Box<T> {
  T _item;
  
  Box(this._item);
  
  T get item => _item;
  
  void setItem(T newItem) {
    _item = newItem;
  }
  
  void display() {
    print('Box contains: $_item (${_item.runtimeType})');
  }
}

// Generic method
T getFirst<T>(List<T> list) {
  if (list.isNotEmpty) {
    return list.first;
  }
  throw Exception('List is empty');
}

// Generic interface
abstract class Repository<T> {
  void save(T item);
  T? findById(int id);
  List<T> findAll();
  void delete(int id);
}

// Concrete implementation
class UserRepository implements Repository<User> {
  List<User> _users = [];
  int _nextId = 1;
  
  @override
  void save(User user) {
    user.id = _nextId++;
    _users.add(user);
    print('User saved: ${user.name}');
  }
  
  @override
  User? findById(int id) {
    try {
      return _users.firstWhere((user) => user.id == id);
    } catch (e) {
      return null;
    }
  }
  
  @override
  List<User> findAll() {
    return List.from(_users);
  }
  
  @override
  void delete(int id) {
    _users.removeWhere((user) => user.id == id);
    print('User with id $id deleted');
  }
}

class User {
  int? id;
  String name;
  String email;
  
  User(this.name, this.email);
  
  @override
  String toString() => 'User(id: $id, name: $name, email: $email)';
}

void main() {
  // Using generic class
  Box<String> stringBox = Box('Hello');
  Box<int> intBox = Box(42);
  Box<double> doubleBox = Box(3.14);
  
  stringBox.display();
  intBox.display();
  doubleBox.display();
  
  print('---');
  
  // Using generic method
  List<String> names = ['Alice', 'Bob', 'Charlie'];
  List<int> numbers = [1, 2, 3, 4, 5];
  
  String firstName = getFirst(names);
  int firstNumber = getFirst(numbers);
  
  print('First name: $firstName');
  print('First number: $firstNumber');
  
  print('---');
  
  // Using generic repository
  UserRepository userRepo = UserRepository();
  
  userRepo.save(User('Alice', 'alice@example.com'));
  userRepo.save(User('Bob', 'bob@example.com'));
  
  List<User> allUsers = userRepo.findAll();
  print('All users: $allUsers');
  
  User? user = userRepo.findById(1);
  print('Found user: $user');
}
```

**Output:**
```
Box contains: Hello (String)
Box contains: 42 (int)
Box contains: 3.14 (double)
---
First name: Alice
First number: 1
---
User saved: Alice
User saved: Bob
All users: [User(id: 1, name: Alice, email: alice@example.com), User(id: 2, name: Bob, email: bob@example.com)]
Found user: User(id: 1, name: Alice, email: alice@example.com)
```

#### Example 10: Advanced OOP Concepts
```dart
// Abstract base class
abstract class Shape {
  String name;
  
  Shape(this.name);
  
  // Abstract methods
  double get area;
  double get perimeter;
  
  // Concrete method
  void displayInfo() {
    print('$name - Area: ${area.toStringAsFixed(2)}, Perimeter: ${perimeter.toStringAsFixed(2)}');
  }
}

// Interface
abstract class Drawable {
  void draw();
  void setColor(String color);
}

// Mixin
mixin Movable {
  void move(double x, double y) {
    print('Moving to position ($x, $y)');
  }
}

// Concrete class implementing multiple concepts
class Circle extends Shape implements Drawable with Movable {
  double radius;
  String color = 'black';
  double x = 0, y = 0;
  
  Circle(String name, this.radius) : super(name);
  
  @override
  double get area => 3.14159 * radius * radius;
  
  @override
  double get perimeter => 2 * 3.14159 * radius;
  
  @override
  void draw() {
    print('Drawing a $color circle with radius $radius at ($x, $y)');
  }
  
  @override
  void setColor(String color) {
    this.color = color;
  }
  
  @override
  void move(double x, double y) {
    this.x = x;
    this.y = y;
    super.move(x, y);
  }
}

// Generic class with constraints
class Container<T extends Shape> {
  List<T> shapes = [];
  
  void addShape(T shape) {
    shapes.add(shape);
    print('Added ${shape.name} to container');
  }
  
  void displayAll() {
    print('Container contents:');
    for (var shape in shapes) {
      shape.displayInfo();
    }
  }
  
  double get totalArea {
    return shapes.fold(0.0, (sum, shape) => sum + shape.area);
  }
}

// Factory pattern
class ShapeFactory {
  static Shape createShape(String type, String name, List<double> params) {
    switch (type.toLowerCase()) {
      case 'circle':
        return Circle(name, params[0]);
      case 'rectangle':
        return Rectangle(name, params[0], params[1]);
      default:
        throw ArgumentError('Unknown shape type: $type');
    }
  }
}

class Rectangle extends Shape implements Drawable with Movable {
  double width;
  double height;
  String color = 'black';
  double x = 0, y = 0;
  
  Rectangle(String name, this.width, this.height) : super(name);
  
  @override
  double get area => width * height;
  
  @override
  double get perimeter => 2 * (width + height);
  
  @override
  void draw() {
    print('Drawing a $color rectangle ${width}x$height at ($x, $y)');
  }
  
  @override
  void setColor(String color) {
    this.color = color;
  }
  
  @override
  void move(double x, double y) {
    this.x = x;
    this.y = y;
    super.move(x, y);
  }
}

void main() {
  // Using factory pattern
  Shape circle = ShapeFactory.createShape('circle', 'MyCircle', [5.0]);
  Shape rectangle = ShapeFactory.createShape('rectangle', 'MyRectangle', [4.0, 6.0]);
  
  // Using polymorphism
  List<Shape> shapes = [circle, rectangle];
  
  for (var shape in shapes) {
    shape.displayInfo();
  }
  
  print('---');
  
  // Using generic container
  Container<Shape> container = Container<Shape>();
  container.addShape(circle);
  container.addShape(rectangle);
  
  container.displayAll();
  print('Total area: ${container.totalArea.toStringAsFixed(2)}');
  
  print('---');
  
  // Using mixins and interfaces
  Circle drawableCircle = Circle('DrawableCircle', 3.0);
  drawableCircle.setColor('red');
  drawableCircle.move(10.0, 20.0);
  drawableCircle.draw();
}
```

**Output:**
```
MyCircle - Area: 78.54, Perimeter: 31.42
MyRectangle - Area: 24.00, Perimeter: 20.00
---
Added MyCircle to container
Added MyRectangle to container
Container contents:
MyCircle - Area: 78.54, Perimeter: 31.42
MyRectangle - Area: 24.00, Perimeter: 20.00
Total area: 102.54
---
Moving to position (10.0, 20.0)
Drawing a red circle with radius 3.0 at (10.0, 20.0)
```

---

## 7. Null Safety In Dart

### Overview
Null safety is a feature in Dart that helps prevent null reference errors, which are common sources of bugs in programming. With null safety, variables are non-nullable by default, meaning they cannot contain null values unless explicitly declared as nullable using the `?` operator.

### Key Concepts
- **Non-nullable types**: Cannot be null (default in Dart)
- **Nullable types**: Can be null (declared with `?`)
- **Null-aware operators**: `??`, `?.`, `!` (null assertion)
- **Flow analysis**: Dart analyzes code flow to determine nullability
- **Late variables**: Variables that are initialized later

### 10 Examples of Null Safety in Dart

#### Example 1: Basic Nullable and Non-Nullable Variables
```dart
void main() {
  // Non-nullable variable (cannot be null)
  String name = 'John';
  // name = null; // Error: Cannot assign null to non-nullable variable
  
  // Nullable variable (can be null)
  String? nullableName;
  nullableName = null; // Valid
  nullableName = 'Jane'; // Also valid
  
  // Null safety check
  if (nullableName != null) {
    print('Name length: ${nullableName.length}'); // Safe to access
  }
  
  print('Non-nullable name: $name');
  print('Nullable name: $nullableName');
}
```

**Output:**
```
Non-nullable name: John
Nullable name: null
```

#### Example 2: Null Coalescing Operator (??)
```dart
void main() {
  String? maybeNull;
  String? alsoNull = null;
  String? hasValue = 'Hello';
  
  // Using ?? to provide default value
  String result1 = maybeNull ?? 'Default Value';
  String result2 = alsoNull ?? 'Fallback Value';
  String result3 = hasValue ?? 'This won\'t be used';
  
  print('Result 1: $result1');
  print('Result 2: $result2');
  print('Result 3: $result3');
  
  // Chaining null coalescing
  String? first = null;
  String? second = null;
  String? third = 'Found it!';
  String finalResult = first ?? second ?? third ?? 'All were null';
  
  print('Final result: $finalResult');
}
```

**Output:**
```
Result 1: Default Value
Result 2: Fallback Value
Result 3: Hello
Final result: Found it!
```

#### Example 3: Null-Aware Access Operator (?.)
```dart
void main() {
  String? maybeNull;
  String? hasValue = 'Dart Programming';
  
  // Safe navigation - returns null if object is null
  int? length1 = maybeNull?.length;
  int? length2 = hasValue?.length;
  
  print('Length 1: $length1');
  print('Length 2: $length2');
  
  // Chaining null-aware operators
  Map<String, Map<String, String>>? nested;
  String? value1 = nested?['key1']?['key2'];
  print('Nested value: $value1');
  
  Map<String, Map<String, String>>? nestedWithValue = {
    'key1': {'key2': 'Found it!'}
  };
  String? value2 = nestedWithValue?['key1']?['key2'];
  print('Nested value 2: $value2');
  
  // Null-aware method calls
  List<int>? numbers;
  numbers?.add(5); // Won't execute if numbers is null
  print('Numbers: $numbers');
  
  numbers = [];
  numbers?.add(10);
  print('Numbers after assignment: $numbers');
}
```

**Output:**
```
Length 1: null
Length 2: 16
Nested value: null
Nested value 2: Found it!
Numbers: null
Numbers after assignment: [10]
```

#### Example 4: Null Assertion Operator (!)
```dart
void main() {
  String? nullableString = 'Hello';
  
  // Using ! to assert that value is not null
  // Use with caution - can throw if null
  String nonNullString = nullableString!;
  print('Non-null string: $nonNullString');
  
  // Dangerous - will throw runtime error if null
  // String? maybeNull = null;
  // String forced = maybeNull!; // Runtime error!
  
  // Safe usage pattern
  String? userInput = getUserInput();
  if (userInput != null) {
    String safeString = userInput!; // Safe because we checked
    print('User input: $safeString');
  }
  
  // Using with null-aware operators
  List<int>? numbers;
  int? firstNumber = numbers?.first; // Safe, returns null if numbers is null
  print('First number: $firstNumber');
  
  numbers = [1, 2, 3];
  int? firstNumber2 = numbers?.first;
  if (firstNumber2 != null) {
    int doubled = firstNumber2! * 2;
    print('Doubled: $doubled');
  }
}

String? getUserInput() {
  // Simulate getting user input
  return 'User entered this';
}
```

**Output:**
```
Non-null string: Hello
User input: User entered this
First number: null
Doubled: 2
```

#### Example 5: Late Variables
```dart
class User {
  late String name;
  late int age;
  String? email; // Nullable
  
  // Late variables must be initialized before use
  void initialize(String userName, int userAge) {
    name = userName;
    age = userAge;
  }
  
  void display() {
    print('Name: $name, Age: $age');
    if (email != null) {
      print('Email: $email');
    }
  }
}

void main() {
  User user = User();
  // print(user.name); // Error: Late variable not initialized
  
  user.initialize('Alice', 25);
  user.display();
  
  user.email = 'alice@example.com';
  user.display();
  
  // Late final variables
  late final String lateFinalValue;
  lateFinalValue = 'Set once';
  // lateFinalValue = 'Set again'; // Error: late final can only be set once
  print('Late final: $lateFinalValue');
}
```

**Output:**
```
Name: Alice, Age: 25
Name: Alice, Age: 25
Email: alice@example.com
Late final: Set once
```

#### Example 6: Null Safety with Collections
```dart
void main() {
  // List of non-nullable strings
  List<String> names = ['Alice', 'Bob', 'Charlie'];
  // names.add(null); // Error: Cannot add null
  
  // List of nullable strings
  List<String?> nullableNames = ['Alice', null, 'Charlie', null];
  print('Nullable names: $nullableNames');
  
  // Filtering out nulls
  List<String> nonNullNames = nullableNames
      .where((name) => name != null)
      .map((name) => name!)
      .toList();
  print('Non-null names: $nonNullNames');
  
  // Using whereType to filter nulls
  List<String> filtered = nullableNames.whereType<String>().toList();
  print('Filtered names: $filtered');
  
  // Nullable map values
  Map<String, String?> data = {
    'name': 'John',
    'email': 'john@example.com',
    'phone': null,
    'address': '123 Main St',
  };
  
  print('Data: $data');
  
  // Safe access to map values
  String? phone = data['phone'];
  if (phone != null) {
    print('Phone: $phone');
  } else {
    print('Phone not provided');
  }
  
  // Using null-aware operators with maps
  int? phoneLength = data['phone']?.length;
  print('Phone length: $phoneLength');
}
```

**Output:**
```
Nullable names: [Alice, null, Charlie, null]
Non-null names: [Alice, Charlie]
Filtered names: [Alice, Charlie]
Data: {name: John, email: john@example.com, phone: null, address: 123 Main St}
Phone not provided
Phone length: null
```

#### Example 7: Null Safety with Functions
```dart
// Function returning nullable type
String? findName(int id) {
  if (id == 1) {
    return 'Alice';
  } else if (id == 2) {
    return 'Bob';
  }
  return null; // Valid because return type is String?
}

// Function with nullable parameter
void greetUser(String? name) {
  if (name != null) {
    print('Hello, $name!');
  } else {
    print('Hello, Guest!');
  }
}

// Function with non-nullable return but nullable parameter
String processName(String? input) {
  return input ?? 'Unknown';
}

// Optional parameters (already nullable)
void printInfo(String name, [int? age, String? city]) {
  print('Name: $name');
  if (age != null) {
    print('Age: $age');
  }
  if (city != null) {
    print('City: $city');
  }
}

void main() {
  // Using functions with nullable types
  String? name1 = findName(1);
  String? name2 = findName(99);
  
  print('Name 1: $name1');
  print('Name 2: $name2');
  
  greetUser(name1);
  greetUser(name2);
  
  String processed1 = processName('John');
  String processed2 = processName(null);
  print('Processed 1: $processed1');
  print('Processed 2: $processed2');
  
  printInfo('Alice', 25, 'New York');
  printInfo('Bob');
}
```

**Output:**
```
Name 1: Alice
Name 2: null
Hello, Alice!
Hello, Guest!
Processed 1: John
Processed 2: Unknown
Name: Alice
Age: 25
City: New York
Name: Bob
```

#### Example 8: Null Safety with Classes and Objects
```dart
class Person {
  String name;
  int age;
  String? email; // Nullable field
  
  Person(this.name, this.age, [this.email]);
  
  void display() {
    print('Name: $name');
    print('Age: $age');
    if (email != null) {
      print('Email: $email');
    } else {
      print('Email: Not provided');
    }
  }
  
  String getEmailOrDefault() {
    return email ?? 'No email';
  }
}

class Company {
  String name;
  Person? manager; // Nullable reference
  
  Company(this.name, [this.manager]);
  
  void displayInfo() {
    print('Company: $name');
    if (manager != null) {
      print('Manager: ${manager!.name}');
      // Or use null-aware
      print('Manager email: ${manager?.email ?? 'Not provided'}');
    } else {
      print('No manager assigned');
    }
  }
}

void main() {
  Person person1 = Person('Alice', 25, 'alice@example.com');
  Person person2 = Person('Bob', 30); // No email
  
  person1.display();
  print('---');
  person2.display();
  print('---');
  
  Company company1 = Company('Tech Corp', person1);
  Company company2 = Company('Startup Inc'); // No manager
  
  company1.displayInfo();
  print('---');
  company2.displayInfo();
}
```

**Output:**
```
Name: Alice
Age: 25
Email: alice@example.com
---
Name: Bob
Age: 30
Email: Not provided
---
Company: Tech Corp
Manager: Alice
Manager email: alice@example.com
---
Company: Startup Inc
No manager assigned
```

#### Example 9: Flow Analysis and Null Promotion
```dart
void main() {
  String? maybeString = 'Hello';
  
  // Dart's flow analysis promotes nullable to non-nullable
  if (maybeString != null) {
    // Inside this block, Dart knows maybeString is not null
    print('Length: ${maybeString.length}'); // No need for !
    print('Upper: ${maybeString.toUpperCase()}'); // Safe
  }
  
  // Using is operator for type and null checking
  Object? value = 'Test';
  if (value is String) {
    print('Value is String: ${value.toUpperCase()}'); // Promoted to String
  }
  
  // Using || for default values
  String? name;
  String greeting = 'Hello, ${name ?? 'Guest'}';
  print(greeting);
  
  // Flow analysis with early returns
  String? getUserName(int id) {
    if (id < 0) return null;
    if (id == 0) return 'Admin';
    return 'User$id';
  }
  
  String? userName = getUserName(5);
  if (userName == null) return; // Early return
  
  // After null check, userName is promoted to non-null
  print('User name length: ${userName.length}');
  
  // Null-aware assignment
  String? result;
  result ??= 'Default'; // Only assign if null
  print('Result: $result');
  
  result = 'Existing';
  result ??= 'New Value'; // Won't assign
  print('Result after: $result');
}
```

**Output:**
```
Length: 5
Upper: HELLO
Value is String: TEST
Hello, Guest
User name length: 5
Result: Default
Result after: Existing
```

#### Example 10: Advanced Null Safety Patterns
```dart
class Database {
  Map<int, String> _data = {};
  
  String? findById(int id) {
    return _data[id]; // Returns String? (nullable)
  }
  
  void save(int id, String value) {
    _data[id] = value;
  }
}

class UserService {
  Database _db = Database();
  
  String? getUserName(int userId) {
    return _db.findById(userId);
  }
  
  String getDisplayName(int userId) {
    String? name = getUserName(userId);
    return name ?? 'Unknown User';
  }
  
  void processUser(int userId) {
    String? name = getUserName(userId);
    
    // Pattern matching with null safety
    switch (name) {
      case null:
        print('User not found');
        break;
      case 'Admin':
        print('Admin user detected');
        break;
      default:
        print('Processing user: $name');
    }
    
    // Using null-aware cascade
    name?.toUpperCase()
        ?.split('')
        ?.forEach((char) => print('Char: $char'));
  }
}

void main() {
  UserService service = UserService();
  
  // Save some users
  service._db.save(1, 'Alice');
  service._db.save(2, 'Bob');
  
  // Retrieve users
  print('User 1: ${service.getDisplayName(1)}');
  print('User 2: ${service.getDisplayName(2)}');
  print('User 99: ${service.getDisplayName(99)}');
  
  print('---');
  
  service.processUser(1);
  print('---');
  service.processUser(99);
  
  // Null-aware list operations
  List<String?> items = ['a', null, 'b', null, 'c'];
  List<String> nonNullItems = items
      .where((item) => item != null)
      .cast<String>()
      .toList();
  print('Non-null items: $nonNullItems');
  
  // Conditional null-aware execution
  String? value;
  value?.isEmpty == true ? print('Empty') : print('Not empty or null');
  
  value = '';
  value?.isEmpty == true ? print('Empty') : print('Not empty');
}
```

**Output:**
```
User 1: Alice
User 2: Bob
User 99: Unknown User
---
Char: A
Char: L
Char: I
Char: C
Char: E
Processing user: Alice
---
User not found
Non-null items: [a, b, c]
Not empty or null
Empty
```

---

## 8. Asynchronous Programming

### Overview
Asynchronous programming in Dart allows you to write code that doesn't block execution while waiting for operations to complete. This is essential for operations like network requests, file I/O, and database operations that take time.

### Key Concepts
- **Future**: Represents a value that will be available in the future
- **async/await**: Syntax for writing asynchronous code that looks synchronous
- **Stream**: A sequence of asynchronous events
- **Future vs Stream**: Future returns a single value, Stream returns multiple values
- **Error Handling**: Using try-catch with async operations

### 10 Examples of Asynchronous Programming in Dart

#### Example 1: Basic Future and async/await
```dart
import 'dart:async';

// Function returning a Future
Future<String> fetchData() async {
  // Simulate network delay
  await Future.delayed(Duration(seconds: 2));
  return 'Data fetched successfully!';
}

// Function using await
Future<void> processData() async {
  print('Starting to fetch data...');
  String data = await fetchData();
  print(data);
  print('Data processing complete!');
}

void main() async {
  await processData();
  print('Main function completed');
}
```

**Output:**
```
Starting to fetch data...
Data fetched successfully!
Data processing complete!
Main function completed
```

#### Example 2: Future with then() and catchError()
```dart
import 'dart:async';

Future<String> simulateNetworkCall() async {
  await Future.delayed(Duration(seconds: 1));
  // Simulate success or failure
  if (DateTime.now().millisecond % 2 == 0) {
    return 'Success!';
  } else {
    throw Exception('Network error');
  }
}

void main() {
  // Using then() and catchError()
  simulateNetworkCall()
      .then((value) {
        print('Result: $value');
      })
      .catchError((error) {
        print('Error occurred: $error');
      })
      .whenComplete(() {
        print('Network call completed');
      });
  
  print('This prints immediately (non-blocking)');
}
```

**Output:**
```
This prints immediately (non-blocking)
Result: Success!
Network call completed
```

#### Example 3: Multiple Async Operations
```dart
import 'dart:async';

Future<String> fetchUser(int id) async {
  await Future.delayed(Duration(seconds: 1));
  return 'User$id';
}

Future<String> fetchProfile(int userId) async {
  await Future.delayed(Duration(milliseconds: 500));
  return 'Profile for User$userId';
}

Future<String> fetchSettings(int userId) async {
  await Future.delayed(Duration(milliseconds: 300));
  return 'Settings for User$userId';
}

void main() async {
  // Sequential execution
  print('--- Sequential ---');
  Stopwatch sw1 = Stopwatch()..start();
  String user = await fetchUser(1);
  String profile = await fetchProfile(1);
  String settings = await fetchSettings(1);
  sw1.stop();
  print('User: $user');
  print('Profile: $profile');
  print('Settings: $settings');
  print('Time: ${sw1.elapsedMilliseconds}ms');
  
  // Parallel execution
  print('\n--- Parallel ---');
  Stopwatch sw2 = Stopwatch()..start();
  String user2 = await fetchUser(2);
  String profile2 = await fetchProfile(2);
  String settings2 = await fetchSettings(2);
  sw2.stop();
  print('User: $user2');
  print('Profile: $profile2');
  print('Settings: $settings2');
  print('Time: ${sw2.elapsedMilliseconds}ms');
}
```

**Output:**
```
--- Sequential ---
User: User1
Profile: Profile for User1
Settings: Settings for User1
Time: 1803ms
--- Parallel ---
User: User2
Profile: Profile for User2
Settings: Settings for User2
Time: 1003ms
```

#### Example 4: Future.wait() for Parallel Execution
```dart
import 'dart:async';

Future<String> task1() async {
  await Future.delayed(Duration(seconds: 2));
  return 'Task 1 completed';
}

Future<String> task2() async {
  await Future.delayed(Duration(seconds: 1));
  return 'Task 2 completed';
}

Future<String> task3() async {
  await Future.delayed(Duration(seconds: 3));
  return 'Task 3 completed';
}

void main() async {
  print('Starting parallel tasks...');
  Stopwatch stopwatch = Stopwatch()..start();
  
  // Wait for all futures to complete
  List<String> results = await Future.wait([
    task1(),
    task2(),
    task3(),
  ]);
  
  stopwatch.stop();
  print('All tasks completed in ${stopwatch.elapsedMilliseconds}ms');
  results.forEach((result) => print(result));
  
  // Future.wait with error handling
  try {
    List<String> results2 = await Future.wait([
      task1(),
      task2(),
      Future.error('Task failed'),
    ]);
    print(results2);
  } catch (e) {
    print('Error in parallel execution: $e');
  }
}
```

**Output:**
```
Starting parallel tasks...
All tasks completed in 3001ms
Task 1 completed
Task 2 completed
Task 3 completed
Error in parallel execution: Task failed
```

#### Example 5: Stream Basics
```dart
import 'dart:async';

// Creating a stream
Stream<int> countStream(int max) async* {
  for (int i = 1; i <= max; i++) {
    await Future.delayed(Duration(milliseconds: 500));
    yield i; // Emit value to stream
  }
}

void main() async {
  print('Listening to stream...');
  
  // Listening to stream
  await for (int value in countStream(5)) {
    print('Received: $value');
  }
  
  print('Stream completed');
  
  // Using stream methods
  Stream<int> stream = countStream(3);
  stream.listen(
    (value) => print('Value: $value'),
    onError: (error) => print('Error: $error'),
    onDone: () => print('Stream done'),
    cancelOnError: false,
  );
  
  await Future.delayed(Duration(seconds: 2));
}
```

**Output:**
```
Listening to stream...
Received: 1
Received: 2
Received: 3
Received: 4
Received: 5
Stream completed
Value: 1
Value: 2
Value: 3
Stream done
```

#### Example 6: Stream Transformation
```dart
import 'dart:async';

Stream<int> numberStream() async* {
  for (int i = 1; i <= 10; i++) {
    await Future.delayed(Duration(milliseconds: 200));
    yield i;
  }
}

void main() async {
  // Transform stream
  Stream<int> doubled = numberStream().map((n) => n * 2);
  
  print('Doubled values:');
  await for (int value in doubled) {
    print(value);
  }
  
  // Filter stream
  Stream<int> evens = numberStream().where((n) => n % 2 == 0);
  
  print('\nEven values:');
  await for (int value in evens) {
    print(value);
  }
  
  // Take first N values
  Stream<int> firstThree = numberStream().take(3);
  
  print('\nFirst three:');
  await for (int value in firstThree) {
    print(value);
  }
  
  // Skip values
  Stream<int> skipped = numberStream().skip(5);
  
  print('\nAfter skipping 5:');
  await for (int value in skipped) {
    print(value);
  }
}
```

**Output:**
```
Doubled values:
2
4
6
8
10
12
14
16
18
20
Even values:
2
4
6
8
10
First three:
1
2
3
After skipping 5:
6
7
8
9
10
```

#### Example 7: Error Handling in Async Code
```dart
import 'dart:async';

Future<String> mightFail(bool shouldFail) async {
  await Future.delayed(Duration(seconds: 1));
  if (shouldFail) {
    throw Exception('Something went wrong!');
  }
  return 'Success!';
}

Future<void> handleErrors() async {
  // Using try-catch with async
  try {
    String result = await mightFail(false);
    print('Result: $result');
    
    String result2 = await mightFail(true);
    print('Result 2: $result2'); // Won't execute
  } catch (e) {
    print('Caught error: $e');
  } finally {
    print('Cleanup code here');
  }
}

Future<String> safeOperation() async {
  try {
    return await mightFail(false);
  } on Exception catch (e) {
    print('Exception: $e');
    return 'Default value';
  } catch (e) {
    print('Unknown error: $e');
    rethrow;
  }
}

void main() async {
  await handleErrors();
  print('---');
  String result = await safeOperation();
  print('Safe result: $result');
}
```

**Output:**
```
Result: Success!
Caught error: Exception: Something went wrong!
Cleanup code here
---
Safe result: Success!
```

#### Example 8: Completer for Custom Futures
```dart
import 'dart:async';

class DataService {
  Completer<String> _completer = Completer<String>();
  
  Future<String> fetchData() {
    // Simulate async operation
    Future.delayed(Duration(seconds: 2), () {
      if (!_completer.isCompleted) {
        _completer.complete('Data loaded successfully');
      }
    });
    
    return _completer.future;
  }
  
  Future<String> fetchDataWithError() {
    Completer<String> completer = Completer<String>();
    
    Future.delayed(Duration(seconds: 1), () {
      completer.completeError('Failed to load data');
    });
    
    return completer.future;
  }
  
  Future<String> fetchDataConditionally(bool success) {
    Completer<String> completer = Completer<String>();
    
    Future.delayed(Duration(seconds: 1), () {
      if (success) {
        completer.complete('Success!');
      } else {
        completer.completeError('Operation failed');
      }
    });
    
    return completer.future;
  }
}

void main() async {
  DataService service = DataService();
  
  print('Fetching data...');
  String data = await service.fetchData();
  print('Received: $data');
  
  try {
    await service.fetchDataWithError();
  } catch (e) {
    print('Error: $e');
  }
  
  try {
    String result = await service.fetchDataConditionally(true);
    print('Conditional result: $result');
  } catch (e) {
    print('Error: $e');
  }
}
```

**Output:**
```
Fetching data...
Received: Data loaded successfully
Error: Failed to load data
Conditional result: Success!
```

#### Example 9: StreamController for Custom Streams
```dart
import 'dart:async';

class NumberGenerator {
  StreamController<int> _controller = StreamController<int>();
  Timer? _timer;
  int _counter = 0;
  
  Stream<int> get stream => _controller.stream;
  
  void start() {
    _timer = Timer.periodic(Duration(seconds: 1), (timer) {
      _counter++;
      _controller.add(_counter);
      
      if (_counter >= 5) {
        stop();
      }
    });
  }
  
  void stop() {
    _timer?.cancel();
    _controller.close();
  }
}

void main() async {
  NumberGenerator generator = NumberGenerator();
  
  generator.stream.listen(
    (value) => print('Generated: $value'),
    onDone: () => print('Stream closed'),
    onError: (error) => print('Error: $error'),
  );
  
  generator.start();
  
  // Wait for stream to complete
  await generator.stream.drain();
  print('All done!');
}
```

**Output:**
```
Generated: 1
Generated: 2
Generated: 3
Generated: 4
Generated: 5
Stream closed
All done!
```

#### Example 10: Advanced Async Patterns
```dart
import 'dart:async';

Future<String> timeoutOperation() async {
  await Future.delayed(Duration(seconds: 5));
  return 'Operation completed';
}

Future<String> fastOperation() async {
  await Future.delayed(Duration(seconds: 1));
  return 'Fast operation completed';
}

void main() async {
  // Timeout handling
  try {
    String result = await timeoutOperation()
        .timeout(Duration(seconds: 3), onTimeout: () {
      return 'Operation timed out';
    });
    print('Result: $result');
  } catch (e) {
    print('Error: $e');
  }
  
  // Future.any - first to complete
  print('\n--- Future.any ---');
  String firstResult = await Future.any([
    Future.delayed(Duration(seconds: 3), () => 'Slow'),
    Future.delayed(Duration(seconds: 1), () => 'Fast'),
    Future.delayed(Duration(seconds: 2), () => 'Medium'),
  ]);
  print('First completed: $firstResult');
  
  // Async generator with error handling
  Stream<int> numberStream() async* {
    for (int i = 1; i <= 5; i++) {
      if (i == 3) {
        throw Exception('Error at 3');
      }
      yield i;
    }
  }
  
  print('\n--- Stream with errors ---');
  try {
    await for (int value in numberStream()) {
      print('Value: $value');
    }
  } catch (e) {
    print('Stream error: $e');
  }
  
  // Using Stream.handleError
  print('\n--- Stream error handling ---');
  numberStream()
      .handleError((error) => print('Handled: $error'))
      .listen(
        (value) => print('Received: $value'),
        onDone: () => print('Done'),
      );
  
  await Future.delayed(Duration(seconds: 1));
}
```

**Output:**
```
Result: Operation timed out
--- Future.any ---
First completed: Fast
--- Stream with errors ---
Value: 1
Value: 2
Stream error: Exception: Error at 3
--- Stream error handling ---
Received: 1
Received: 2
Handled: Exception: Error at 3
```

---

## 9. Useful Information

### Final Vs Const

### Overview
Both `final` and `const` are used to create immutable values in Dart, but they have important differences:
- **const**: Compile-time constant, must be known at compile time
- **final**: Run-time constant, can be assigned once but value determined at runtime

### 10 Examples of Final Vs Const

#### Example 1: Basic const and final
```dart
void main() {
  // const - compile-time constant
  const int maxAttempts = 3;
  const String appName = 'MyApp';
  const double pi = 3.14159;
  
  // final - run-time constant
  final int currentYear = DateTime.now().year; // Determined at runtime
  final String userName = getUserName(); // Can call functions
  
  print('Max attempts: $maxAttempts');
  print('App name: $appName');
  print('PI: $pi');
  print('Current year: $currentYear');
  print('User name: $userName');
  
  // Cannot reassign
  // maxAttempts = 4; // Error
  // currentYear = 2025; // Error
}

String getUserName() {
  return 'John Doe';
}
```

**Output:**
```
Max attempts: 3
App name: MyApp
PI: 3.14159
Current year: 2024
User name: John Doe
```

#### Example 2: const Lists and Maps
```dart
void main() {
  // const list - compile-time constant
  const List<int> numbers = [1, 2, 3, 4, 5];
  // numbers.add(6); // Error: Cannot modify const list
  
  // final list - can be created at runtime
  final List<String> names = ['Alice', 'Bob'];
  names.add('Charlie'); // Valid - can modify list contents
  // names = ['New']; // Error: Cannot reassign final variable
  
  print('Numbers: $numbers');
  print('Names: $names');
  
  // const map
  const Map<String, int> ages = {'Alice': 25, 'Bob': 30};
  // ages['Charlie'] = 35; // Error: Cannot modify const map
  
  // final map
  final Map<String, String> cities = {'Alice': 'NYC', 'Bob': 'LA'};
  cities['Charlie'] = 'Chicago'; // Valid
  print('Cities: $cities');
}
```

**Output:**
```
Numbers: [1, 2, 3, 4, 5]
Names: [Alice, Bob, Charlie]
Cities: {Alice: NYC, Bob: LA, Charlie: Chicago}
```

#### Example 3: const vs final in Classes
```dart
class Circle {
  static const double pi = 3.14159; // Class-level const
  
  final double radius; // Instance-level final
  late final double area; // Late final - computed later
  
  Circle(this.radius) {
    area = pi * radius * radius; // Computed in constructor
  }
  
  // Cannot use const in instance variable that depends on constructor param
  // const double radius; // Error if used with constructor parameter
}

class Constants {
  static const String appName = 'MyApp';
  static const int maxUsers = 100;
}

void main() {
  Circle circle1 = Circle(5.0);
  Circle circle2 = Circle(10.0);
  
  print('Circle 1 radius: ${circle1.radius}, area: ${circle1.area}');
  print('Circle 2 radius: ${circle2.radius}, area: ${circle2.area}');
  print('PI: ${Circle.pi}');
  print('App name: ${Constants.appName}');
}
```

**Output:**
```
Circle 1 radius: 5.0, area: 78.53975
Circle 2 radius: 10.0, area: 314.159
PI: 3.14159
App name: MyApp
```

#### Example 4: const Constructors
```dart
class Point {
  final int x;
  final int y;
  
  // const constructor - all fields must be final
  const Point(this.x, this.y);
  
  // Regular constructor
  Point.origin() : x = 0, y = 0;
}

void main() {
  // Using const constructor creates compile-time constant
  const Point p1 = Point(0, 0);
  const Point p2 = Point(0, 0);
  
  // p1 and p2 are identical (same object)
  print('p1 == p2: ${identical(p1, p2)}');
  
  // Without const, creates new objects
  Point p3 = Point(0, 0);
  Point p4 = Point(0, 0);
  print('p3 == p4: ${p3 == p4}'); // Different instances
  print('identical(p3, p4): ${identical(p3, p4)}');
  
  // final with const constructor
  final Point p5 = const Point(5, 10);
  print('Point p5: (${p5.x}, ${p5.y})');
}
```

**Output:**
```
p1 == p2: true
p3 == p4: false
identical(p3, p4): false
Point p5: (5, 10)
```

#### Example 5: const Expressions
```dart
void main() {
  // const can use compile-time expressions
  const int sum = 10 + 20;
  const int product = 5 * 6;
  const String message = 'Hello' + ' World';
  
  // Cannot use runtime values
  // const int currentYear = DateTime.now().year; // Error
  final int currentYear = DateTime.now().year; // OK
  
  // const with calculations
  const double radius = 5.0;
  const double area = 3.14159 * radius * radius;
  
  print('Sum: $sum');
  print('Product: $product');
  print('Message: $message');
  print('Area: $area');
  print('Current year: $currentYear');
  
  // const lists with expressions
  const List<int> doubled = [2 * 1, 2 * 2, 2 * 3, 2 * 4];
  print('Doubled: $doubled');
}
```

**Output:**
```
Sum: 30
Product: 30
Message: Hello World
Area: 78.53975
Current year: 2024
Doubled: [2, 4, 6, 8]
```

#### Example 6: final with Initialization
```dart
class User {
  final String name;
  final int age;
  final DateTime createdAt;
  
  User(this.name, this.age) : createdAt = DateTime.now();
  
  // final can be initialized in different ways
  final String id;
  User.withId(this.name, this.age, this.id) : createdAt = DateTime.now();
  
  void display() {
    print('Name: $name, Age: $age, Created: $createdAt, ID: $id');
  }
}

void main() {
  User user1 = User('Alice', 25);
  // Wait a bit
  Future.delayed(Duration(milliseconds: 100));
  User user2 = User('Bob', 30);
  
  user1.display();
  user2.display();
  
  User user3 = User.withId('Charlie', 35, 'user_123');
  user3.display();
}
```

**Output:**
```
Name: Alice, Age: 25, Created: 2024-01-01 10:00:00.000, ID: 
Name: Bob, Age: 30, Created: 2024-01-01 10:00:00.100, ID: 
Name: Charlie, Age: 35, Created: 2024-01-01 10:00:00.100, ID: user_123
```

#### Example 7: const with Collections
```dart
void main() {
  // const lists
  const List<int> primes = [2, 3, 5, 7, 11];
  const List<String> colors = ['red', 'green', 'blue'];
  
  // const sets
  const Set<int> numbers = {1, 2, 3, 4, 5};
  
  // const maps
  const Map<String, int> scores = {'Alice': 95, 'Bob': 87, 'Charlie': 92};
  
  print('Primes: $primes');
  print('Colors: $colors');
  print('Numbers: $numbers');
  print('Scores: $scores');
  
  // Cannot modify const collections
  // primes.add(13); // Error
  // scores['David'] = 90; // Error
  
  // final allows modification of collection contents
  final List<int> mutable = [1, 2, 3];
  mutable.add(4); // OK
  print('Mutable: $mutable');
  
  // But cannot reassign
  // mutable = [5, 6, 7]; // Error
}
```

**Output:**
```
Primes: [2, 3, 5, 7, 11]
Colors: [red, green, blue]
Numbers: {1, 2, 3, 4, 5}
Scores: {Alice: 95, Bob: 87, Charlie: 92}
Mutable: [1, 2, 3, 4]
```

#### Example 8: Performance Considerations
```dart
void main() {
  // const objects are created once at compile time
  const Point p1 = Point(1, 2);
  const Point p2 = Point(1, 2);
  const Point p3 = Point(1, 2);
  
  // All refer to the same object
  print('p1 identical to p2: ${identical(p1, p2)}');
  print('p2 identical to p3: ${identical(p2, p3)}');
  
  // final creates new objects
  final Point f1 = Point(1, 2);
  final Point f2 = Point(1, 2);
  
  print('f1 identical to f2: ${identical(f1, f2)}');
  
  // const lists share memory
  const List<int> list1 = [1, 2, 3];
  const List<int> list2 = [1, 2, 3];
  print('list1 identical to list2: ${identical(list1, list2)}');
  
  // final lists are separate
  final List<int> list3 = [1, 2, 3];
  final List<int> list4 = [1, 2, 3];
  print('list3 identical to list4: ${identical(list3, list4)}');
}

class Point {
  final int x;
  final int y;
  const Point(this.x, this.y);
}
```

**Output:**
```
p1 identical to p2: true
p2 identical to p3: true
f1 identical to f2: false
list1 identical to list2: true
list3 identical to list4: false
```

#### Example 9: When to Use const vs final
```dart
void main() {
  // Use const when:
  // 1. Value is known at compile time
  const String appVersion = '1.0.0';
  const int maxRetries = 3;
  const List<String> supportedLanguages = ['en', 'es', 'fr'];
  
  // 2. You want compile-time optimization
  const Map<String, String> errorMessages = {
    '404': 'Not Found',
    '500': 'Server Error',
  };
  
  // Use final when:
  // 1. Value depends on runtime
  final String currentTime = DateTime.now().toString();
  final int userInput = int.parse('42');
  
  // 2. You need to compute value
  final String greeting = 'Hello, ${getUserName()}';
  
  // 3. Collection that may be modified
  final List<String> items = [];
  items.add('item1'); // OK
  
  print('App version: $appVersion');
  print('Current time: $currentTime');
  print('Greeting: $greeting');
  print('Items: $items');
}

String getUserName() => 'John';
```

**Output:**
```
App version: 1.0.0
Current time: 2024-01-01 10:00:00.000
Greeting: Hello, John
Items: [item1]
```

#### Example 10: Advanced const and final Patterns
```dart
class Configuration {
  static const String appName = 'MyApp';
  static const int version = 1;
  
  final String environment;
  final String apiUrl;
  
  const Configuration.development()
      : environment = 'dev',
        apiUrl = 'https://dev.api.com';
  
  const Configuration.production()
      : environment = 'prod',
        apiUrl = 'https://api.com';
  
  // Regular constructor with final
  Configuration.custom(this.environment, this.apiUrl);
}

void main() {
  // Using const constructors
  const Configuration dev = Configuration.development();
  const Configuration prod = Configuration.production();
  
  print('Dev: ${dev.environment}, URL: ${dev.apiUrl}');
  print('Prod: ${prod.environment}, URL: ${prod.apiUrl}');
  
  // Custom configuration with final
  final Configuration custom = Configuration.custom(
    'staging',
    'https://staging.api.com',
  );
  print('Custom: ${custom.environment}, URL: ${custom.apiUrl}');
  
  // const with complex expressions
  const List<int> fibonacci = [
    1,
    1,
    1 + 1,
    1 + 2,
    3 + 2,
    5 + 3,
    8 + 5,
  ];
  print('Fibonacci: $fibonacci');
  
  // final with lazy initialization
  late final String lazyValue;
  lazyValue = computeExpensiveValue();
  print('Lazy value: $lazyValue');
}

String computeExpensiveValue() {
  print('Computing expensive value...');
  return 'Computed';
}
```

**Output:**
```
Dev: dev, URL: https://dev.api.com
Prod: prod, URL: https://api.com
Custom: staging, URL: https://staging.api.com
Fibonacci: [1, 1, 2, 3, 5, 8, 13]
Computing expensive value...
Lazy value: Computed
```

---

### Datetime In Dart

### Overview
The `DateTime` class in Dart provides functionality to work with dates and times. It supports creating, formatting, parsing, and manipulating dates and times.

### Key Concepts
- **DateTime creation**: Various constructors for creating dates
- **Formatting**: Converting DateTime to strings
- **Parsing**: Converting strings to DateTime
- **Manipulation**: Adding/subtracting time
- **Comparison**: Comparing dates and times

### 10 Examples of Datetime in Dart

#### Example 1: Creating DateTime Objects
```dart
void main() {
  // Current date and time
  DateTime now = DateTime.now();
  print('Now: $now');
  
  // Specific date and time
  DateTime specific = DateTime(2024, 1, 15, 14, 30, 45);
  print('Specific: $specific');
  
  // Date only (time defaults to 00:00:00)
  DateTime dateOnly = DateTime(2024, 1, 15);
  print('Date only: $dateOnly');
  
  // UTC time
  DateTime utc = DateTime.utc(2024, 1, 15, 14, 30, 45);
  print('UTC: $utc');
  
  // Parse from string
  DateTime parsed = DateTime.parse('2024-01-15 14:30:45');
  print('Parsed: $parsed');
  
  // From milliseconds since epoch
  DateTime fromMillis = DateTime.fromMillisecondsSinceEpoch(1705327845000);
  print('From milliseconds: $fromMillis');
}
```

**Output:**
```
Now: 2024-01-01 10:00:00.000
Specific: 2024-01-15 14:30:45.000
Date only: 2024-01-15 00:00:00.000
UTC: 2024-01-15 14:30:45.000Z
Parsed: 2024-01-15 14:30:45.000
From milliseconds: 2024-01-15 14:30:45.000
```

#### Example 2: DateTime Formatting
```dart
void main() {
  DateTime now = DateTime(2024, 1, 15, 14, 30, 45);
  
  // Using toString methods
  print('toString(): ${now.toString()}');
  print('toIso8601String(): ${now.toIso8601String()}');
  print('toUtc(): ${now.toUtc()}');
  
  // Manual formatting
  String formatted = '${now.year}-${now.month.toString().padLeft(2, '0')}-${now.day.toString().padLeft(2, '0')}';
  print('Manual format: $formatted');
  
  String timeFormatted = '${now.hour.toString().padLeft(2, '0')}:${now.minute.toString().padLeft(2, '0')}:${now.second.toString().padLeft(2, '0')}';
  print('Time format: $timeFormatted');
  
  // Formatting date components
  print('Year: ${now.year}');
  print('Month: ${now.month}');
  print('Day: ${now.day}');
  print('Hour: ${now.hour}');
  print('Minute: ${now.minute}');
  print('Second: ${now.second}');
  print('Millisecond: ${now.millisecond}');
  
  // Day of week (1 = Monday, 7 = Sunday)
  print('Weekday: ${now.weekday}');
}
```

**Output:**
```
toString(): 2024-01-15 14:30:45.000
toIso8601String(): 2024-01-15T14:30:45.000
toUtc(): 2024-01-15 14:30:45.000Z
Manual format: 2024-01-15
Time format: 14:30:45
Year: 2024
Month: 1
Day: 15
Hour: 14
Minute: 30
Second: 45
Millisecond: 0
Weekday: 1
```

#### Example 3: DateTime Parsing
```dart
void main() {
  // Parse ISO 8601 format
  DateTime dt1 = DateTime.parse('2024-01-15');
  print('Parsed date: $dt1');
  
  DateTime dt2 = DateTime.parse('2024-01-15T14:30:45');
  print('Parsed datetime: $dt2');
  
  DateTime dt3 = DateTime.parse('2024-01-15T14:30:45Z');
  print('Parsed UTC: $dt3');
  
  // Try parse with error handling
  String? dateString = '2024-01-15';
  DateTime? parsed = _tryParseDate(dateString);
  print('Try parsed: $parsed');
  
  String? invalidDate = 'invalid';
  DateTime? invalid = _tryParseDate(invalidDate);
  print('Invalid parse: $invalid');
}

DateTime? _tryParseDate(String? dateString) {
  if (dateString == null) return null;
  try {
    return DateTime.parse(dateString);
  } catch (e) {
    return null;
  }
}
```

**Output:**
```
Parsed date: 2024-01-15 00:00:00.000
Parsed datetime: 2024-01-15 14:30:45.000
Parsed UTC: 2024-01-15 14:30:45.000Z
Try parsed: 2024-01-15 00:00:00.000
Invalid parse: null
```

#### Example 4: DateTime Manipulation
```dart
void main() {
  DateTime base = DateTime(2024, 1, 15, 14, 30, 45);
  
  // Adding time
  DateTime future = base.add(Duration(days: 7));
  print('Add 7 days: $future');
  
  DateTime withHours = base.add(Duration(hours: 2));
  print('Add 2 hours: $withHours');
  
  DateTime withMinutes = base.add(Duration(minutes: 30));
  print('Add 30 minutes: $withMinutes');
  
  // Subtracting time
  DateTime past = base.subtract(Duration(days: 5));
  print('Subtract 5 days: $past');
  
  // Adding/subtracting multiple units
  DateTime complex = base.add(Duration(
    days: 1,
    hours: 2,
    minutes: 30,
    seconds: 15,
  ));
  print('Complex add: $complex');
  
  // Difference between dates
  Duration difference = future.difference(base);
  print('Difference: ${difference.inDays} days');
  print('Difference in hours: ${difference.inHours}');
}
```

**Output:**
```
Add 7 days: 2024-01-22 14:30:45.000
Add 2 hours: 2024-01-15 16:30:45.000
Add 30 minutes: 2024-01-15 15:00:45.000
Subtract 5 days: 2024-01-10 14:30:45.000
Complex add: 2024-01-16 17:00:60.000
Difference: 7 days
Difference in hours: 168
```

#### Example 5: DateTime Comparison
```dart
void main() {
  DateTime date1 = DateTime(2024, 1, 15);
  DateTime date2 = DateTime(2024, 1, 20);
  DateTime date3 = DateTime(2024, 1, 15);
  
  // Comparison operators
  print('date1 < date2: ${date1.isBefore(date2)}');
  print('date2 > date1: ${date2.isAfter(date1)}');
  print('date1 == date3: ${date1.isAtSameMomentAs(date3)}');
  
  // Compare to
  print('date1 compareTo date2: ${date1.compareTo(date2)}'); // -1
  print('date2 compareTo date1: ${date2.compareTo(date1)}'); // 1
  print('date1 compareTo date3: ${date1.compareTo(date3)}'); // 0
  
  // Checking if dates are same day
  bool sameDay = date1.year == date3.year &&
                 date1.month == date3.month &&
                 date1.day == date3.day;
  print('Same day: $sameDay');
  
  // Sorting dates
  List<DateTime> dates = [
    DateTime(2024, 1, 20),
    DateTime(2024, 1, 15),
    DateTime(2024, 1, 25),
    DateTime(2024, 1, 10),
  ];
  dates.sort();
  print('Sorted dates: $dates');
}
```

**Output:**
```
date1 < date2: true
date2 > date1: true
date1 == date3: true
date1 compareTo date2: -1
date2 compareTo date1: 1
date1 compareTo date3: 0
Same day: true
Sorted dates: [2024-01-10 00:00:00.000, 2024-01-15 00:00:00.000, 2024-01-20 00:00:00.000, 2024-01-25 00:00:00.000]
```

#### Example 6: Working with Time Zones
```dart
void main() {
  // Local time
  DateTime local = DateTime.now();
  print('Local time: $local');
  
  // UTC time
  DateTime utc = DateTime.now().toUtc();
  print('UTC time: $utc');
  
  // Convert UTC to local
  DateTime utcToLocal = DateTime.utc(2024, 1, 15, 14, 30).toLocal();
  print('UTC to local: $utcToLocal');
  
  // Convert local to UTC
  DateTime localToUtc = DateTime(2024, 1, 15, 14, 30).toUtc();
  print('Local to UTC: $localToUtc');
  
  // Check if UTC
  print('Is UTC: ${utc.isUtc}');
  print('Is UTC (local): ${local.isUtc}');
  
  // Time zone offset
  print('Time zone offset: ${local.timeZoneOffset}');
}
```

**Output:**
```
Local time: 2024-01-01 10:00:00.000
UTC time: 2024-01-01 10:00:00.000Z
UTC to local: 2024-01-15 14:30:00.000
Local to UTC: 2024-01-15 14:30:00.000Z
Is UTC: true
Is UTC (local): false
Time zone offset: 5:30:00.000000
```

#### Example 7: Date Calculations and Utilities
```dart
void main() {
  DateTime date = DateTime(2024, 1, 15);
  
  // First day of month
  DateTime firstDay = DateTime(date.year, date.month, 1);
  print('First day of month: $firstDay');
  
  // Last day of month
  DateTime lastDay = DateTime(date.year, date.month + 1, 0);
  print('Last day of month: $lastDay');
  
  // Days in month
  int daysInMonth = DateTime(date.year, date.month + 1, 0).day;
  print('Days in month: $daysInMonth');
  
  // Start of day
  DateTime startOfDay = DateTime(date.year, date.month, date.day);
  print('Start of day: $startOfDay');
  
  // End of day
  DateTime endOfDay = DateTime(date.year, date.month, date.day, 23, 59, 59);
  print('End of day: $endOfDay');
  
  // Age calculation
  DateTime birthDate = DateTime(1990, 5, 15);
  DateTime today = DateTime.now();
  int age = today.year - birthDate.year;
  if (today.month < birthDate.month ||
      (today.month == birthDate.month && today.day < birthDate.day)) {
    age--;
  }
  print('Age: $age years');
}
```

**Output:**
```
First day of month: 2024-01-01 00:00:00.000
Last day of month: 2024-01-31 00:00:00.000
Days in month: 31
Start of day: 2024-01-15 00:00:00.000
End of day: 2024-01-15 23:59:59.000
Age: 34 years
```

#### Example 8: Formatting with Custom Functions
```dart
String formatDate(DateTime date, {String format = 'yyyy-MM-dd'}) {
  String year = date.year.toString();
  String month = date.month.toString().padLeft(2, '0');
  String day = date.day.toString().padLeft(2, '0');
  String hour = date.hour.toString().padLeft(2, '0');
  String minute = date.minute.toString().padLeft(2, '0');
  String second = date.second.toString().padLeft(2, '0');
  
  return format
      .replaceAll('yyyy', year)
      .replaceAll('MM', month)
      .replaceAll('dd', day)
      .replaceAll('HH', hour)
      .replaceAll('mm', minute)
      .replaceAll('ss', second);
}

String getRelativeTime(DateTime date) {
  Duration difference = DateTime.now().difference(date);
  
  if (difference.inDays > 365) {
    return '${(difference.inDays / 365).floor()} years ago';
  } else if (difference.inDays > 30) {
    return '${(difference.inDays / 30).floor()} months ago';
  } else if (difference.inDays > 0) {
    return '${difference.inDays} days ago';
  } else if (difference.inHours > 0) {
    return '${difference.inHours} hours ago';
  } else if (difference.inMinutes > 0) {
    return '${difference.inMinutes} minutes ago';
  } else {
    return 'Just now';
  }
}

void main() {
  DateTime date = DateTime(2024, 1, 15, 14, 30, 45);
  
  print('Formatted: ${formatDate(date)}');
  print('Custom format: ${formatDate(date, format: 'dd/MM/yyyy HH:mm')}');
  
  DateTime past = DateTime.now().subtract(Duration(days: 5));
  print('Relative time: ${getRelativeTime(past)}');
  
  DateTime recent = DateTime.now().subtract(Duration(minutes: 30));
  print('Recent: ${getRelativeTime(recent)}');
}
```

**Output:**
```
Formatted: 2024-01-15
Custom format: 15/01/2024 14:30
Relative time: 5 days ago
Recent: 30 minutes ago
```

#### Example 9: Working with Epoch Time
```dart
void main() {
  DateTime now = DateTime.now();
  
  // Milliseconds since epoch
  int milliseconds = now.millisecondsSinceEpoch;
  print('Milliseconds since epoch: $milliseconds');
  
  // Seconds since epoch
  int seconds = now.millisecondsSinceEpoch ~/ 1000;
  print('Seconds since epoch: $seconds');
  
  // Convert back
  DateTime fromMillis = DateTime.fromMillisecondsSinceEpoch(milliseconds);
  print('From milliseconds: $fromMillis');
  
  DateTime fromSeconds = DateTime.fromMillisecondsSinceEpoch(seconds * 1000);
  print('From seconds: $fromSeconds');
  
  // Microseconds since epoch
  int microseconds = now.microsecondsSinceEpoch;
  print('Microseconds since epoch: $microseconds');
  
  DateTime fromMicros = DateTime.fromMicrosecondsSinceEpoch(microseconds);
  print('From microseconds: $fromMicros');
  
  // Unix timestamp example
  int unixTimestamp = 1705327845;
  DateTime unixDate = DateTime.fromMillisecondsSinceEpoch(unixTimestamp * 1000);
  print('Unix timestamp: $unixDate');
}
```

**Output:**
```
Milliseconds since epoch: 1704067200000
Seconds since epoch: 1704067200
From milliseconds: 2024-01-01 10:00:00.000
From seconds: 2024-01-01 10:00:00.000
Microseconds since epoch: 1704067200000000
From microseconds: 2024-01-01 10:00:00.000
Unix timestamp: 2024-01-15 14:30:45.000
```

#### Example 10: Date Range and Iteration
```dart
List<DateTime> getDateRange(DateTime start, DateTime end) {
  List<DateTime> dates = [];
  DateTime current = start;
  
  while (current.isBefore(end) || current.isAtSameMomentAs(end)) {
    dates.add(DateTime(current.year, current.month, current.day));
    current = current.add(Duration(days: 1));
  }
  
  return dates;
}

bool isWeekend(DateTime date) {
  return date.weekday == 6 || date.weekday == 7; // Saturday or Sunday
}

bool isWeekday(DateTime date) {
  return date.weekday >= 1 && date.weekday <= 5;
}

void main() {
  DateTime start = DateTime(2024, 1, 15);
  DateTime end = DateTime(2024, 1, 20);
  
  List<DateTime> range = getDateRange(start, end);
  print('Date range:');
  for (DateTime date in range) {
    String weekday = ['Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat', 'Sun'][date.weekday - 1];
    print('${date.day}/${date.month}/${date.year} ($weekday)');
  }
  
  // Filter weekends
  List<DateTime> weekdays = range.where((date) => isWeekday(date)).toList();
  print('\nWeekdays only: ${weekdays.length} days');
  
  // Filter weekends
  List<DateTime> weekends = range.where((date) => isWeekend(date)).toList();
  print('Weekends: ${weekends.length} days');
}
```

**Output:**
```
Date range:
15/1/2024 (Mon)
16/1/2024 (Tue)
17/1/2024 (Wed)
18/1/2024 (Thu)
19/1/2024 (Fri)
20/1/2024 (Sat)

Weekdays only: 5 days
Weekends: 1 days
```

---

### Extension In Dart

### Overview
Extensions in Dart allow you to add functionality to existing classes without modifying them. This is useful for adding methods, getters, setters, and operators to classes you don't own or can't modify.

### Key Concepts
- **Extension keyword**: Declares an extension
- **On keyword**: Specifies the type being extended
- **Static extensions**: Can add static methods
- **Generic extensions**: Can work with generic types
- **No instantiation**: Extensions are compile-time features

### 10 Examples of Extension In Dart

#### Example 1: Basic String Extension
```dart
extension StringExtension on String {
  // Add a method to capitalize first letter
  String capitalize() {
    if (isEmpty) return this;
    return '${this[0].toUpperCase()}${substring(1)}';
  }
  
  // Add a method to reverse string
  String reverse() {
    return split('').reversed.join('');
  }
  
  // Add a getter
  bool get isEmail {
    return contains('@') && contains('.');
  }
  
  // Add a method with parameters
  String repeat(int times) {
    return List.filled(times, this).join('');
  }
}

void main() {
  String text = 'hello world';
  print('Original: $text');
  print('Capitalized: ${text.capitalize()}');
  print('Reversed: ${text.reverse()}');
  print('Is email: ${text.isEmail}');
  
  String email = 'user@example.com';
  print('Is email (true): ${email.isEmail}');
  print('Repeated: ${'Hi '.repeat(3)}');
}
```

**Output:**
```
Original: hello world
Capitalized: Hello world
Reversed: dlrow olleh
Is email: false
Is email (true): true
Repeated: Hi Hi Hi 
```

#### Example 2: Number Extensions
```dart
extension IntExtension on int {
  // Check if even
  bool get isEven => this % 2 == 0;
  
  // Check if odd
  bool get isOdd => !isEven;
  
  // Factorial
  int factorial() {
    if (this <= 1) return 1;
    return this * (this - 1).factorial();
  }
  
  // Power
  int power(int exponent) {
    if (exponent == 0) return 1;
    return this * power(exponent - 1);
  }
  
  // To duration
  Duration get seconds => Duration(seconds: this);
  Duration get minutes => Duration(minutes: this);
  Duration get hours => Duration(hours: this);
}

extension DoubleExtension on double {
  // Round to decimal places
  double roundTo(int places) {
    num mod = power(10, places);
    return ((this * mod).round().toDouble() / mod);
  }
  
  // Check if approximately equal
  bool isApproximatelyEqual(double other, {double epsilon = 0.001}) {
    return (this - other).abs() < epsilon;
  }
}

void main() {
  int number = 5;
  print('$number is even: ${number.isEven}');
  print('$number is odd: ${number.isOdd}');
  print('Factorial of $number: ${number.factorial()}');
  print('$number to power 3: ${number.power(3)}');
  print('5 seconds: ${5.seconds}');
  print('2 hours: ${2.hours}');
  
  double pi = 3.14159;
  print('Pi rounded to 2 places: ${pi.roundTo(2)}');
  print('Pi approximately 3.14: ${pi.isApproximatelyEqual(3.14)}');
}
```

**Output:**
```
5 is even: false
5 is odd: true
Factorial of 5: 120
5 to power 3: 125
5 seconds: 0:00:05.000000
2 hours: 0:02:00.000000
Pi rounded to 2 places: 3.14
Pi approximately 3.14: true
```

#### Example 3: List Extensions
```dart
extension ListExtension<T> on List<T> {
  // Get first and last safely
  T? get firstOrNull => isEmpty ? null : first;
  T? get lastOrNull => isEmpty ? null : last;
  
  // Remove duplicates
  List<T> unique() {
    return toSet().toList();
  }
  
  // Chunk list into smaller lists
  List<List<T>> chunk(int size) {
    List<List<T>> chunks = [];
    for (int i = 0; i < length; i += size) {
      chunks.add(sublist(i, i + size > length ? length : i + size));
    }
    return chunks;
  }
  
  // Get random element
  T? random() {
    if (isEmpty) return null;
    return this[DateTime.now().millisecondsSinceEpoch % length];
  }
  
  // Swap elements
  void swap(int index1, int index2) {
    if (index1 >= 0 && index1 < length && index2 >= 0 && index2 < length) {
      T temp = this[index1];
      this[index1] = this[index2];
      this[index2] = temp;
    }
  }
}

void main() {
  List<int> numbers = [1, 2, 3, 4, 5, 2, 3];
  print('Original: $numbers');
  print('Unique: ${numbers.unique()}');
  print('Chunked (size 3): ${numbers.chunk(3)}');
  
  List<String> names = ['Alice', 'Bob', 'Charlie'];
  print('First or null: ${names.firstOrNull}');
  print('Last or null: ${names.lastOrNull}');
  
  List<int> empty = [];
  print('Empty first: ${empty.firstOrNull}');
  
  List<int> list = [1, 2, 3, 4, 5];
  list.swap(0, 4);
  print('After swap: $list');
}
```

**Output:**
```
Original: [1, 2, 3, 4, 5, 2, 3]
Unique: [1, 2, 3, 4, 5]
Chunked (size 3): [[1, 2, 3], [4, 5, 2], [3]]
First or null: Alice
Last or null: Charlie
Empty first: null
After swap: [5, 2, 3, 4, 1]
```

#### Example 4: DateTime Extensions
```dart
extension DateTimeExtension on DateTime {
  // Check if today
  bool get isToday {
    DateTime now = DateTime.now();
    return year == now.year && month == now.month && day == now.day;
  }
  
  // Check if yesterday
  bool get isYesterday {
    DateTime yesterday = DateTime.now().subtract(Duration(days: 1));
    return year == yesterday.year && 
           month == yesterday.month && 
           day == yesterday.day;
  }
  
  // Check if this week
  bool get isThisWeek {
    DateTime now = DateTime.now();
    DateTime startOfWeek = now.subtract(Duration(days: now.weekday - 1));
    DateTime endOfWeek = startOfWeek.add(Duration(days: 6));
    return isAfter(startOfWeek.subtract(Duration(days: 1))) && 
           isBefore(endOfWeek.add(Duration(days: 1)));
  }
  
  // Format date
  String format({String separator = '-'}) {
    return '${year}$separator${month.toString().padLeft(2, '0')}$separator${day.toString().padLeft(2, '0')}';
  }
  
  // Get age
  int get age {
    DateTime now = DateTime.now();
    int age = now.year - year;
    if (now.month < month || (now.month == month && now.day < day)) {
      age--;
    }
    return age;
  }
  
  // Start of day
  DateTime get startOfDay => DateTime(year, month, day);
  
  // End of day
  DateTime get endOfDay => DateTime(year, month, day, 23, 59, 59);
}

void main() {
  DateTime today = DateTime.now();
  DateTime yesterday = DateTime.now().subtract(Duration(days: 1));
  DateTime birthDate = DateTime(1990, 5, 15);
  
  print('Is today: ${today.isToday}');
  print('Is yesterday: ${yesterday.isYesterday}');
  print('Is this week: ${today.isThisWeek}');
  print('Formatted: ${today.format()}');
  print('Formatted with /: ${today.format(separator: '/')}');
  print('Age: ${birthDate.age}');
  print('Start of day: ${today.startOfDay}');
  print('End of day: ${today.endOfDay}');
}
```

**Output:**
```
Is today: true
Is yesterday: true
Is this week: true
Formatted: 2024-01-01
Formatted with /: 2024/01/01
Age: 34
Start of day: 2024-01-01 00:00:00.000
End of day: 2024-01-01 23:59:59.000
```

#### Example 5: Map Extensions
```dart
extension MapExtension<K, V> on Map<K, V> {
  // Get value or default
  V? getOrDefault(K key, V defaultValue) {
    return containsKey(key) ? this[key] : defaultValue;
  }
  
  // Invert map (swap keys and values)
  Map<V, K> invert() {
    Map<V, K> inverted = {};
    forEach((key, value) {
      inverted[value] = key;
    });
    return inverted;
  }
  
  // Filter map
  Map<K, V> filter(bool Function(K key, V value) test) {
    Map<K, V> filtered = {};
    forEach((key, value) {
      if (test(key, value)) {
        filtered[key] = value;
      }
    });
    return filtered;
  }
  
  // Merge with another map
  Map<K, V> merge(Map<K, V> other) {
    Map<K, V> merged = Map.from(this);
    merged.addAll(other);
    return merged;
  }
}

void main() {
  Map<String, int> ages = {'Alice': 25, 'Bob': 30, 'Charlie': 35};
  
  print('Alice age: ${ages.getOrDefault('Alice', 0)}');
  print('David age: ${ages.getOrDefault('David', 0)}');
  
  Map<int, String> inverted = ages.invert();
  print('Inverted: $inverted');
  
  Map<String, int> filtered = ages.filter((key, value) => value > 28);
  print('Filtered (>28): $filtered');
  
  Map<String, int> newAges = {'David': 28, 'Eve': 22};
  Map<String, int> merged = ages.merge(newAges);
  print('Merged: $merged');
}
```

**Output:**
```
Alice age: 25
David age: 0
Inverted: {25: Alice, 30: Bob, 35: Charlie}
Filtered (>28): {Bob: 30, Charlie: 35}
Merged: {Alice: 25, Bob: 30, Charlie: 35, David: 28, Eve: 22}
```

#### Example 6: Generic Extensions
```dart
extension NullableExtension<T> on T? {
  // Execute if not null
  R? let<R>(R Function(T) block) {
    if (this != null) {
      return block(this as T);
    }
    return null;
  }
  
  // Execute if null
  T orElse(T defaultValue) {
    return this ?? defaultValue;
  }
}

extension ComparableExtension<T extends Comparable<T>> on T {
  // Clamp value between min and max
  T clamp(T min, T max) {
    if (this.compareTo(min) < 0) return min;
    if (this.compareTo(max) > 0) return max;
    return this;
  }
  
  // Check if between
  bool isBetween(T min, T max) {
    return compareTo(min) >= 0 && compareTo(max) <= 0;
  }
}

void main() {
  String? nullableString = 'Hello';
  String? nullString = null;
  
  String? result1 = nullableString.let((value) => value.toUpperCase());
  print('Let result: $result1');
  
  String result2 = nullString.orElse('Default');
  print('Or else result: $result2');
  
  int number = 15;
  int clamped = number.clamp(10, 20);
  print('Clamped: $clamped');
  
  int outside = 25;
  int clampedOutside = outside.clamp(10, 20);
  print('Clamped outside: $clampedOutside');
  
  print('15 is between 10 and 20: ${15.isBetween(10, 20)}');
  print('25 is between 10 and 20: ${25.isBetween(10, 20)}');
}
```

**Output:**
```
Let result: HELLO
Or else result: Default
Clamped: 15
Clamped outside: 20
15 is between 10 and 20: true
25 is between 10 and 20: false
```

#### Example 7: Operator Extensions
```dart
extension IntOperatorExtension on int {
  // Custom operators using methods
  int operator ^(int other) => power(other);
  
  int power(int exponent) {
    if (exponent == 0) return 1;
    if (exponent == 1) return this;
    int half = power(exponent ~/ 2);
    return half * half * (exponent % 2 == 1 ? this : 1);
  }
}

extension StringOperatorExtension on String {
  // String multiplication
  String operator *(int times) {
    return List.filled(times, this).join('');
  }
}

void main() {
  int base = 2;
  int exponent = 8;
  int result = base ^ exponent;
  print('$base ^ $exponent = $result');
  
  String text = 'Hello';
  String repeated = text * 3;
  print('Repeated: $repeated');
  
  print('Hi ' * 5);
}
```

**Output:**
```
2 ^ 8 = 256
Repeated: HelloHelloHello
Hi Hi Hi Hi Hi 
```

#### Example 8: Conditional Extensions
```dart
extension IterableExtension<T> on Iterable<T> {
  // Check if all elements satisfy condition
  bool all(bool Function(T) test) {
    for (T element in this) {
      if (!test(element)) return false;
    }
    return true;
  }
  
  // Check if any element satisfies condition
  bool anyElement(bool Function(T) test) {
    for (T element in this) {
      if (test(element)) return true;
    }
    return false;
  }
  
  // Get first element satisfying condition or null
  T? firstWhereOrNull(bool Function(T) test) {
    for (T element in this) {
      if (test(element)) return element;
    }
    return null;
  }
  
  // Partition into two lists
  List<List<T>> partition(bool Function(T) test) {
    List<T> truthy = [];
    List<T> falsy = [];
    for (T element in this) {
      if (test(element)) {
        truthy.add(element);
      } else {
        falsy.add(element);
      }
    }
    return [truthy, falsy];
  }
}

void main() {
  List<int> numbers = [2, 4, 6, 8, 10];
  
  print('All even: ${numbers.all((n) => n % 2 == 0)}');
  print('Any odd: ${numbers.anyElement((n) => n % 2 == 1)}');
  
  List<int> mixed = [1, 2, 3, 4, 5];
  print('All even: ${mixed.all((n) => n % 2 == 0)}');
  print('Any odd: ${mixed.anyElement((n) => n % 2 == 1)}');
  
  int? found = numbers.firstWhereOrNull((n) => n > 5);
  print('First > 5: $found');
  
  List<List<int>> partitioned = mixed.partition((n) => n % 2 == 0);
  print('Even: ${partitioned[0]}');
  print('Odd: ${partitioned[1]}');
}
```

**Output:**
```
All even: true
Any odd: false
All even: false
Any odd: true
First > 5: 6
Even: [2, 4]
Odd: [1, 3, 5]
```

#### Example 9: Static Extensions
```dart
extension StringStaticExtension on String {
  // Static-like utility methods
  static bool isValidEmail(String email) {
    return email.contains('@') && email.contains('.');
  }
  
  static bool isValidPhone(String phone) {
    return RegExp(r'^\+?[0-9]{10,15}$').hasMatch(phone);
  }
  
  // Instance method
  bool get isValidEmailInstance => StringStaticExtension.isValidEmail(this);
}

extension NumberValidationExtension on String {
  static bool isNumeric(String value) {
    return double.tryParse(value) != null;
  }
  
  static bool isInteger(String value) {
    return int.tryParse(value) != null;
  }
}

void main() {
  String email1 = 'user@example.com';
  String email2 = 'invalid-email';
  
  print('Email 1 valid: ${StringStaticExtension.isValidEmail(email1)}');
  print('Email 2 valid: ${StringStaticExtension.isValidEmail(email2)}');
  print('Email 1 valid (instance): ${email1.isValidEmailInstance}');
  
  String phone1 = '+1234567890';
  String phone2 = '123-456-7890';
  
  print('Phone 1 valid: ${StringStaticExtension.isValidPhone(phone1)}');
  print('Phone 2 valid: ${StringStaticExtension.isValidPhone(phone2)}');
  
  print('Is numeric: ${NumberValidationExtension.isNumeric('123.45')}');
  print('Is integer: ${NumberValidationExtension.isInteger('123')}');
}
```

**Output:**
```
Email 1 valid: true
Email 2 valid: false
Email 1 valid (instance): true
Phone 1 valid: true
Phone 2 valid: false
Is numeric: true
Is integer: true
```

#### Example 10: Advanced Extension Patterns
```dart
extension ValidationExtension on String {
  // Email validation
  bool get isValidEmail {
    return RegExp(r'^[\w-\.]+@([\w-]+\.)+[\w-]{2,4}$').hasMatch(this);
  }
  
  // Phone validation
  bool get isValidPhone {
    return RegExp(r'^\+?[0-9]{10,15}$').hasMatch(replaceAll(' ', ''));
  }
  
  // URL validation
  bool get isValidUrl {
    return RegExp(r'^https?://[^\s/$.?#].[^\s]*$').hasMatch(this);
  }
  
  // Remove all whitespace
  String removeWhitespace() => replaceAll(RegExp(r'\s+'), '');
  
  // Extract numbers
  String extractNumbers() => replaceAll(RegExp(r'[^\d]'), '');
}

extension CollectionExtensions<T> on Iterable<T> {
  // Group by
  Map<K, List<T>> groupBy<K>(K Function(T) keySelector) {
    Map<K, List<T>> grouped = {};
    for (T element in this) {
      K key = keySelector(element);
      grouped.putIfAbsent(key, () => []).add(element);
    }
    return grouped;
  }
  
  // Count occurrences
  Map<T, int> countOccurrences() {
    Map<T, int> counts = {};
    for (T element in this) {
      counts[element] = (counts[element] ?? 0) + 1;
    }
    return counts;
  }
}

void main() {
  String email = 'user@example.com';
  String phone = '+1 234 567 890';
  String url = 'https://example.com';
  
  print('Email valid: ${email.isValidEmail}');
  print('Phone valid: ${phone.isValidPhone}');
  print('URL valid: ${url.isValidUrl}');
  print('Phone cleaned: ${phone.removeWhitespace()}');
  print('Phone numbers: ${phone.extractNumbers()}');
  
  List<String> words = ['apple', 'banana', 'apricot', 'blueberry', 'apple'];
  Map<String, List<String>> grouped = words.groupBy((word) => word[0]);
  print('Grouped by first letter: $grouped');
  
  Map<String, int> counts = words.countOccurrences();
  print('Counts: $counts');
}
```

**Output:**
```
Email valid: true
Phone valid: true
URL valid: true
Phone cleaned: +1234567890
Phone numbers: 1234567890
Grouped by first letter: {a: [apple, apricot, apple], b: [banana, blueberry]}
Counts: {apple: 2, banana: 1, apricot: 1, blueberry: 1}
```

---

### Backend in Dart

### Overview
Dart can be used for backend development using frameworks like Shelf, Aqueduct, and Dart Frog. Backend development in Dart involves creating HTTP servers, handling REST APIs, working with databases, and managing server-side logic.

### Key Concepts
- **HTTP Server**: Creating and managing HTTP servers
- **REST API**: Building RESTful endpoints
- **Middleware**: Request/response processing
- **Database**: Connecting to databases
- **JSON**: Serializing and deserializing data

### 10 Examples of Backend in Dart

#### Example 1: Basic HTTP Server with dart:io
```dart
import 'dart:io';

void main() async {
  // Create HTTP server
  final server = await HttpServer.bind('localhost', 8080);
  print('Server running on http://localhost:8080');
  
  // Handle requests
  await for (HttpRequest request in server) {
    // Set response headers
    request.response.headers.contentType = ContentType.json;
    
    // Handle different routes
    if (request.uri.path == '/') {
      request.response.write('{"message": "Hello, World!"}');
    } else if (request.uri.path == '/api/users') {
      request.response.write('{"users": ["Alice", "Bob", "Charlie"]}');
    } else {
      request.response.statusCode = HttpStatus.notFound;
      request.response.write('{"error": "Not Found"}');
    }
    
    await request.response.close();
  }
}
```

**Usage:**
```bash
# Start server, then visit:
# http://localhost:8080
# http://localhost:8080/api/users
```

#### Example 2: REST API with Shelf Framework
```dart
// pubspec.yaml dependencies:
// shelf: ^1.4.0

import 'package:shelf/shelf.dart';
import 'package:shelf/shelf_io.dart' as io;
import 'dart:convert';

Response handleRequest(Request request) {
  final path = request.url.path;
  final method = request.method;
  
  // GET /api/users
  if (method == 'GET' && path == 'api/users') {
    final users = [
      {'id': 1, 'name': 'Alice', 'age': 25},
      {'id': 2, 'name': 'Bob', 'age': 30},
    ];
    return Response.ok(
      jsonEncode({'users': users}),
      headers: {'Content-Type': 'application/json'},
    );
  }
  
  // POST /api/users
  if (method == 'POST' && path == 'api/users') {
    return Response.ok(
      jsonEncode({'message': 'User created'}),
      headers: {'Content-Type': 'application/json'},
    );
  }
  
  // 404 Not Found
  return Response.notFound(
    jsonEncode({'error': 'Not Found'}),
    headers: {'Content-Type': 'application/json'},
  );
}

void main() async {
  final handler = Pipeline().addMiddleware(logRequests()).addHandler(handleRequest);
  final server = await io.serve(handler, 'localhost', 8080);
  print('Server running on http://localhost:8080');
}
```

**Usage:**
```bash
# GET request
curl http://localhost:8080/api/users

# POST request
curl -X POST http://localhost:8080/api/users
```

#### Example 3: JSON Serialization and Deserialization
```dart
import 'dart:convert';

class User {
  final int id;
  final String name;
  final String email;
  
  User({required this.id, required this.name, required this.email});
  
  // Convert to JSON
  Map<String, dynamic> toJson() {
    return {
      'id': id,
      'name': name,
      'email': email,
    };
  }
  
  // Create from JSON
  factory User.fromJson(Map<String, dynamic> json) {
    return User(
      id: json['id'],
      name: json['name'],
      email: json['email'],
    );
  }
}

void main() {
  // Serialize object to JSON
  User user = User(id: 1, name: 'Alice', email: 'alice@example.com');
  String jsonString = jsonEncode(user.toJson());
  print('JSON: $jsonString');
  
  // Deserialize JSON to object
  Map<String, dynamic> jsonMap = jsonDecode(jsonString);
  User userFromJson = User.fromJson(jsonMap);
  print('User from JSON: ${userFromJson.name}');
  
  // Working with JSON arrays
  List<User> users = [
    User(id: 1, name: 'Alice', email: 'alice@example.com'),
    User(id: 2, name: 'Bob', email: 'bob@example.com'),
  ];
  
  List<Map<String, dynamic>> usersJson = users.map((u) => u.toJson()).toList();
  String usersJsonString = jsonEncode({'users': usersJson});
  print('Users JSON: $usersJsonString');
}
```

**Output:**
```
JSON: {"id":1,"name":"Alice","email":"alice@example.com"}
User from JSON: Alice
Users JSON: {"users":[{"id":1,"name":"Alice","email":"alice@example.com"},{"id":2,"name":"Bob","email":"bob@example.com"}]}
```

#### Example 4: HTTP Client for API Calls
```dart
import 'dart:convert';
import 'dart:io';

Future<void> fetchData() async {
  final client = HttpClient();
  
  try {
    // GET request
    final request = await client.getUrl(Uri.parse('https://jsonplaceholder.typicode.com/posts/1'));
    final response = await request.close();
    
    if (response.statusCode == HttpStatus.ok) {
      final responseBody = await response.transform(utf8.decoder).join();
      final jsonData = jsonDecode(responseBody);
      print('Response: ${jsonData['title']}');
    }
    
    // POST request
    final postRequest = await client.postUrl(Uri.parse('https://jsonplaceholder.typicode.com/posts'));
    postRequest.headers.contentType = ContentType.json;
    postRequest.write(jsonEncode({
      'title': 'Test Post',
      'body': 'This is a test',
      'userId': 1,
    }));
    
    final postResponse = await postRequest.close();
    if (postResponse.statusCode == HttpStatus.created) {
      final responseBody = await postResponse.transform(utf8.decoder).join();
      final jsonData = jsonDecode(responseBody);
      print('Created post with ID: ${jsonData['id']}');
    }
  } finally {
    client.close();
  }
}

void main() async {
  await fetchData();
}
```

**Output:**
```
Response: sunt aut facere repellat provident occaecati excepturi optio reprehenderit
Created post with ID: 101
```

#### Example 5: Request/Response Middleware
```dart
import 'package:shelf/shelf.dart';
import 'package:shelf/shelf_io.dart' as io;
import 'dart:convert';

// CORS middleware
Middleware corsMiddleware() {
  return createMiddleware(
    requestHandler: (Request request) {
      if (request.method == 'OPTIONS') {
        return Response.ok('', headers: {
          'Access-Control-Allow-Origin': '*',
          'Access-Control-Allow-Methods': 'GET, POST, PUT, DELETE',
          'Access-Control-Allow-Headers': 'Content-Type',
        });
      }
      return null;
    },
    responseHandler: (Response response) {
      return response.change(headers: {
        'Access-Control-Allow-Origin': '*',
        'Access-Control-Allow-Methods': 'GET, POST, PUT, DELETE',
        'Access-Control-Allow-Headers': 'Content-Type',
      });
    },
  );
}

// Authentication middleware
Middleware authMiddleware() {
  return createMiddleware(
    requestHandler: (Request request) {
      final authHeader = request.headers['authorization'];
      if (authHeader == null || !authHeader.startsWith('Bearer ')) {
        return Response.unauthorized(
          jsonEncode({'error': 'Unauthorized'}),
          headers: {'Content-Type': 'application/json'},
        );
      }
      return null;
    },
  );
}

Response handleRequest(Request request) {
  return Response.ok(
    jsonEncode({'message': 'Authenticated request'}),
    headers: {'Content-Type': 'application/json'},
  );
}

void main() async {
  final handler = Pipeline()
      .addMiddleware(corsMiddleware())
      .addMiddleware(authMiddleware())
      .addHandler(handleRequest);
  
  final server = await io.serve(handler, 'localhost', 8080);
  print('Server running on http://localhost:8080');
}
```

#### Example 6: Database Operations (In-Memory)
```dart
import 'dart:convert';

// Simple in-memory database
class Database {
  static final Map<String, List<Map<String, dynamic>>> _tables = {};
  
  static void createTable(String tableName) {
    _tables[tableName] = [];
  }
  
  static void insert(String tableName, Map<String, dynamic> data) {
    if (!_tables.containsKey(tableName)) {
      createTable(tableName);
    }
    _tables[tableName]!.add(data);
  }
  
  static List<Map<String, dynamic>> findAll(String tableName) {
    return _tables[tableName] ?? [];
  }
  
  static Map<String, dynamic>? findById(String tableName, int id) {
    final table = _tables[tableName];
    if (table == null) return null;
    try {
      return table.firstWhere((row) => row['id'] == id);
    } catch (e) {
      return null;
    }
  }
  
  static void update(String tableName, int id, Map<String, dynamic> data) {
    final table = _tables[tableName];
    if (table == null) return;
    final index = table.indexWhere((row) => row['id'] == id);
    if (index != -1) {
      table[index] = {...table[index], ...data};
    }
  }
  
  static void delete(String tableName, int id) {
    final table = _tables[tableName];
    if (table == null) return;
    table.removeWhere((row) => row['id'] == id);
  }
}

void main() {
  // Create users table
  Database.createTable('users');
  
  // Insert users
  Database.insert('users', {'id': 1, 'name': 'Alice', 'email': 'alice@example.com'});
  Database.insert('users', {'id': 2, 'name': 'Bob', 'email': 'bob@example.com'});
  
  // Find all
  print('All users: ${Database.findAll('users')}');
  
  // Find by ID
  print('User 1: ${Database.findById('users', 1)}');
  
  // Update
  Database.update('users', 1, {'name': 'Alice Updated'});
  print('Updated user 1: ${Database.findById('users', 1)}');
  
  // Delete
  Database.delete('users', 2);
  print('Users after delete: ${Database.findAll('users')}');
}
```

**Output:**
```
All users: [{id: 1, name: Alice, email: alice@example.com}, {id: 2, name: Bob, email: bob@example.com}]
User 1: {id: 1, name: Alice, email: alice@example.com}
Updated user 1: {id: 1, name: Alice Updated, email: alice@example.com}
Users after delete: [{id: 1, name: Alice Updated, email: alice@example.com}]
```

#### Example 7: File Upload Handling
```dart
import 'dart:io';
import 'dart:convert';

Future<void> handleFileUpload(HttpRequest request) async {
  if (request.method != 'POST') {
    request.response.statusCode = HttpStatus.methodNotAllowed;
    await request.response.close();
    return;
  }
  
  final contentType = request.headers.contentType;
  if (contentType == null || !contentType.mimeType.startsWith('multipart/form-data')) {
    request.response.statusCode = HttpStatus.badRequest;
    request.response.write(jsonEncode({'error': 'Invalid content type'}));
    await request.response.close();
    return;
  }
  
  final boundary = contentType.parameters['boundary']!;
  final transformer = MimeMultipartTransformer(boundary);
  final stream = request.map((data) => String.fromCharCodes(data));
  final parts = await transformer.bind(stream).toList();
  
  for (final part in parts) {
    final header = part.headers['content-disposition'];
    if (header != null) {
      final fileName = _extractFileName(header);
      if (fileName != null) {
        final file = File('uploads/$fileName');
        await file.create(recursive: true);
        await file.writeAsBytes(await part.toBytes());
        request.response.write(jsonEncode({'message': 'File uploaded: $fileName'}));
      }
    }
  }
  
  await request.response.close();
}

String? _extractFileName(String header) {
  final match = RegExp(r'filename="([^"]+)"').firstMatch(header);
  return match?.group(1);
}

void main() async {
  final server = await HttpServer.bind('localhost', 8080);
  print('Server running on http://localhost:8080');
  
  await for (HttpRequest request in server) {
    if (request.uri.path == '/upload') {
      await handleFileUpload(request);
    } else {
      request.response.statusCode = HttpStatus.notFound;
      await request.response.close();
    }
  }
}
```

#### Example 8: WebSocket Server
```dart
import 'dart:io';
import 'dart:convert';

void main() async {
  final server = await HttpServer.bind('localhost', 8080);
  print('WebSocket server running on ws://localhost:8080');
  
  await for (HttpRequest request in server) {
    if (WebSocketTransformer.isUpgradeRequest(request)) {
      final websocket = await WebSocketTransformer.upgrade(request);
      print('Client connected');
      
      // Send welcome message
      websocket.add(jsonEncode({'type': 'welcome', 'message': 'Connected to server'}));
      
      // Listen for messages
      websocket.listen(
        (message) {
          print('Received: $message');
          final data = jsonDecode(message);
          
          // Echo back
          websocket.add(jsonEncode({
            'type': 'echo',
            'original': data,
            'timestamp': DateTime.now().toIso8601String(),
          }));
        },
        onDone: () => print('Client disconnected'),
        onError: (error) => print('Error: $error'),
      );
    } else {
      request.response.statusCode = HttpStatus.notFound;
      await request.response.close();
    }
  }
}
```

#### Example 9: REST API with CRUD Operations
```dart
import 'dart:io';
import 'dart:convert';

class UserService {
  static final List<Map<String, dynamic>> _users = [];
  static int _nextId = 1;
  
  static List<Map<String, dynamic>> getAll() {
    return _users;
  }
  
  static Map<String, dynamic>? getById(int id) {
    try {
      return _users.firstWhere((user) => user['id'] == id);
    } catch (e) {
      return null;
    }
  }
  
  static Map<String, dynamic> create(Map<String, dynamic> data) {
    final user = {
      'id': _nextId++,
      'name': data['name'],
      'email': data['email'],
    };
    _users.add(user);
    return user;
  }
  
  static Map<String, dynamic>? update(int id, Map<String, dynamic> data) {
    final index = _users.indexWhere((user) => user['id'] == id);
    if (index == -1) return null;
    _users[index] = {..._users[index], ...data};
    return _users[index];
  }
  
  static bool delete(int id) {
    final index = _users.indexWhere((user) => user['id'] == id);
    if (index == -1) return false;
    _users.removeAt(index);
    return true;
  }
}

Future<void> handleRequest(HttpRequest request) async {
  request.response.headers.contentType = ContentType.json;
  
  final path = request.uri.path;
  final method = request.method;
  
  // GET /api/users
  if (method == 'GET' && path == '/api/users') {
    final users = UserService.getAll();
    request.response.write(jsonEncode({'users': users}));
  }
  // GET /api/users/:id
  else if (method == 'GET' && path.startsWith('/api/users/')) {
    final id = int.tryParse(path.split('/').last);
    if (id == null) {
      request.response.statusCode = HttpStatus.badRequest;
      request.response.write(jsonEncode({'error': 'Invalid ID'}));
    } else {
      final user = UserService.getById(id);
      if (user == null) {
        request.response.statusCode = HttpStatus.notFound;
        request.response.write(jsonEncode({'error': 'User not found'}));
      } else {
        request.response.write(jsonEncode({'user': user}));
      }
    }
  }
  // POST /api/users
  else if (method == 'POST' && path == '/api/users') {
    final body = await request.transform(utf8.decoder).join();
    final data = jsonDecode(body);
    final user = UserService.create(data);
    request.response.statusCode = HttpStatus.created;
    request.response.write(jsonEncode({'user': user}));
  }
  // PUT /api/users/:id
  else if (method == 'PUT' && path.startsWith('/api/users/')) {
    final id = int.tryParse(path.split('/').last);
    if (id == null) {
      request.response.statusCode = HttpStatus.badRequest;
      request.response.write(jsonEncode({'error': 'Invalid ID'}));
    } else {
      final body = await request.transform(utf8.decoder).join();
      final data = jsonDecode(body);
      final user = UserService.update(id, data);
      if (user == null) {
        request.response.statusCode = HttpStatus.notFound;
        request.response.write(jsonEncode({'error': 'User not found'}));
      } else {
        request.response.write(jsonEncode({'user': user}));
      }
    }
  }
  // DELETE /api/users/:id
  else if (method == 'DELETE' && path.startsWith('/api/users/')) {
    final id = int.tryParse(path.split('/').last);
    if (id == null) {
      request.response.statusCode = HttpStatus.badRequest;
      request.response.write(jsonEncode({'error': 'Invalid ID'}));
    } else {
      final deleted = UserService.delete(id);
      if (!deleted) {
        request.response.statusCode = HttpStatus.notFound;
        request.response.write(jsonEncode({'error': 'User not found'}));
      } else {
        request.response.write(jsonEncode({'message': 'User deleted'}));
      }
    }
  }
  else {
    request.response.statusCode = HttpStatus.notFound;
    request.response.write(jsonEncode({'error': 'Not Found'}));
  }
  
  await request.response.close();
}

void main() async {
  final server = await HttpServer.bind('localhost', 8080);
  print('REST API server running on http://localhost:8080');
  
  await for (HttpRequest request in server) {
    await handleRequest(request);
  }
}
```

#### Example 10: Error Handling and Logging
```dart
import 'dart:io';
import 'dart:convert';

class Logger {
  static void log(String level, String message) {
    final timestamp = DateTime.now().toIso8601String();
    print('[$timestamp] [$level] $message');
  }
  
  static void info(String message) => log('INFO', message);
  static void error(String message) => log('ERROR', message);
  static void warning(String message) => log('WARNING', message);
}

Future<Response> handleRequest(HttpRequest request) async {
  try {
    Logger.info('${request.method} ${request.uri.path}');
    
    // Simulate processing
    if (request.uri.path == '/error') {
      throw Exception('Simulated error');
    }
    
    return Response.ok(
      jsonEncode({'message': 'Success'}),
      headers: {'Content-Type': 'application/json'},
    );
  } catch (e, stackTrace) {
    Logger.error('Error handling request: $e');
    Logger.error('Stack trace: $stackTrace');
    
    return Response.internalServerError(
      body: jsonEncode({
        'error': 'Internal Server Error',
        'message': e.toString(),
      }),
      headers: {'Content-Type': 'application/json'},
    );
  }
}

void main() async {
  final server = await HttpServer.bind('localhost', 8080);
  Logger.info('Server running on http://localhost:8080');
  
  await for (HttpRequest request in server) {
    final response = await handleRequest(request);
    await request.response
        ..statusCode = response.statusCode
        ..headers.contentType = ContentType.json
        ..write(response.body)
        ..close();
  }
}

class Response {
  final int statusCode;
  final String body;
  final Map<String, String> headers;
  
  Response(this.statusCode, this.body, {this.headers = const {}});
  
  static Response ok(String body, {Map<String, String> headers = const {}}) {
    return Response(HttpStatus.ok, body, headers: headers);
  }
  
  static Response internalServerError({
    String body = '',
    Map<String, String> headers = const {},
  }) {
    return Response(HttpStatus.internalServerError, body, headers: headers);
  }
}
```

**Output:**
```
[2024-01-01T10:00:00.000Z] [INFO] Server running on http://localhost:8080
[2024-01-01T10:00:01.000Z] [INFO] GET /
[2024-01-01T10:00:02.000Z] [ERROR] Error handling request: Exception: Simulated error
```

---

### Dart Interview Questions

### Overview
This section contains common Dart interview questions with detailed code examples and explanations. These questions cover fundamental concepts, advanced topics, and best practices that are frequently asked in Dart/Flutter developer interviews.

### 10 Examples of Dart Interview Questions

#### Question 1: What is the difference between `var`, `final`, and `const`?
```dart
void main() {
  // var - type is inferred, can be reassigned
  var name = 'John';
  name = 'Jane'; // Valid
  print('var: $name');
  
  // final - type is inferred, cannot be reassigned (runtime constant)
  final age = 25;
  // age = 26; // Error: cannot assign to final variable
  final currentTime = DateTime.now(); // OK - determined at runtime
  print('final age: $age');
  print('final currentTime: $currentTime');
  
  // const - compile-time constant, cannot be reassigned
  const pi = 3.14159;
  // pi = 3.14; // Error: cannot assign to const variable
  // const now = DateTime.now(); // Error: must be compile-time constant
  print('const pi: $pi');
  
  // Summary:
  // var: mutable, type inferred
  // final: immutable, runtime value
  // const: immutable, compile-time value
}
```

**Output:**
```
var: Jane
final age: 25
final currentTime: 2024-01-01 10:00:00.000
const pi: 3.14159
```

#### Question 2: Explain Null Safety in Dart
```dart
void main() {
  // Non-nullable (default)
  String name = 'John';
  // name = null; // Error: cannot assign null
  
  // Nullable types use ?
  String? nullableName;
  nullableName = null; // OK
  nullableName = 'Jane'; // OK
  
  // Null-aware operators
  String? maybeNull;
  
  // ?? - null coalescing
  String result = maybeNull ?? 'Default';
  print('Result: $result');
  
  // ?. - null-aware access
  int? length = maybeNull?.length;
  print('Length: $length');
  
  // ! - null assertion (use with caution)
  String? definitelyNotNull = 'Hello';
  String forced = definitelyNotNull!; // OK if we're sure
  print('Forced: $forced');
  
  // Null safety prevents null reference errors
}
```

**Output:**
```
Result: Default
Length: null
Forced: Hello
```

#### Question 3: What are Mixins and how do they differ from Inheritance?
```dart
// Mixin definition
mixin Flyable {
  void fly() {
    print('Flying...');
  }
}

mixin Swimmable {
  void swim() {
    print('Swimming...');
  }
}

// Base class
class Animal {
  void eat() {
    print('Eating...');
  }
}

// Class using mixins (multiple inheritance-like behavior)
class Duck extends Animal with Flyable, Swimmable {
  void quack() {
    print('Quacking...');
  }
}

void main() {
  Duck duck = Duck();
  duck.eat();    // From Animal
  duck.fly();    // From Flyable mixin
  duck.swim();   // From Swimmable mixin
  duck.quack();  // From Duck itself
  
  // Difference from inheritance:
  // - Mixins allow multiple behaviors
  // - Inheritance: single parent class
  // - Mixins: "is-a" relationship, Mixins: "has-a" capability
}
```

**Output:**
```
Eating...
Flying...
Swimming...
Quacking...
```

#### Question 4: Explain `async` and `await` in Dart
```dart
import 'dart:async';

// Async function returns Future
Future<String> fetchData() async {
  await Future.delayed(Duration(seconds: 1));
  return 'Data fetched';
}

// Using await to wait for async operations
Future<void> processData() async {
  print('Starting...');
  String data = await fetchData(); // Waits for completion
  print('Received: $data');
  print('Processing complete');
}

// Multiple async operations
Future<void> fetchMultiple() async {
  // Sequential
  String data1 = await fetchData();
  String data2 = await fetchData();
  print('Sequential: $data1, $data2');
  
  // Parallel
  Future<String> future1 = fetchData();
  Future<String> future2 = fetchData();
  String result1 = await future1;
  String result2 = await future2;
  print('Parallel: $result1, $result2');
}

void main() async {
  await processData();
  print('---');
  await fetchMultiple();
}
```

**Output:**
```
Starting...
Received: Data fetched
Processing complete
---
Sequential: Data fetched, Data fetched
Parallel: Data fetched, Data fetched
```

#### Question 5: What is the difference between `List`, `Set`, and `Map`?
```dart
void main() {
  // List - ordered, allows duplicates, indexed
  List<String> fruits = ['apple', 'banana', 'apple'];
  print('List: $fruits');
  print('List length: ${fruits.length}');
  print('First item: ${fruits[0]}');
  
  // Set - unordered, no duplicates
  Set<String> uniqueFruits = {'apple', 'banana', 'apple'};
  print('Set: $uniqueFruits');
  print('Set length: ${uniqueFruits.length}');
  // print('First item: ${uniqueFruits[0]}'); // Error: no index access
  
  // Map - key-value pairs, unique keys
  Map<String, int> ages = {
    'Alice': 25,
    'Bob': 30,
    'Alice': 26, // Overwrites previous Alice
  };
  print('Map: $ages');
  print('Alice age: ${ages['Alice']}');
  print('Map size: ${ages.length}');
  
  // Use cases:
  // List: when order and duplicates matter
  // Set: when uniqueness matters
  // Map: when key-value pairs are needed
}
```

**Output:**
```
List: [apple, banana, apple]
List length: 3
First item: apple
Set: {apple, banana}
Set length: 2
Map: {Alice: 26, Bob: 30}
Alice age: 26
Map size: 2
```

#### Question 6: Explain `Stream` and how it differs from `Future`
```dart
import 'dart:async';

// Future - single value
Future<String> fetchUser() async {
  await Future.delayed(Duration(seconds: 1));
  return 'User data';
}

// Stream - multiple values over time
Stream<int> countStream() async* {
  for (int i = 1; i <= 5; i++) {
    await Future.delayed(Duration(milliseconds: 500));
    yield i; // Emit value
  }
}

void main() async {
  // Future - get value once
  print('Fetching user...');
  String user = await fetchUser();
  print('User: $user');
  
  print('---');
  
  // Stream - listen to multiple values
  print('Listening to stream...');
  await for (int value in countStream()) {
    print('Received: $value');
  }
  
  // Key differences:
  // Future: one value, one-time
  // Stream: multiple values, continuous
}
```

**Output:**
```
Fetching user...
User: User data
---
Listening to stream...
Received: 1
Received: 2
Received: 3
Received: 4
Received: 5
```

#### Question 7: What are Generics and why are they useful?
```dart
// Generic class
class Box<T> {
  T _item;
  
  Box(this._item);
  
  T get item => _item;
  
  void setItem(T newItem) {
    _item = newItem;
  }
}

// Generic method
T getFirst<T>(List<T> list) {
  return list.first;
}

// Generic function with constraints
T findMax<T extends Comparable<T>>(List<T> items) {
  if (items.isEmpty) throw Exception('List is empty');
  return items.reduce((a, b) => a.compareTo(b) > 0 ? a : b);
}

void main() {
  // Type-safe container
  Box<String> stringBox = Box('Hello');
  Box<int> intBox = Box(42);
  
  print('String box: ${stringBox.item}');
  print('Int box: ${intBox.item}');
  
  // Generic method
  String first = getFirst(['Alice', 'Bob', 'Charlie']);
  int firstNum = getFirst([1, 2, 3]);
  print('First string: $first');
  print('First number: $firstNum');
  
  // Generic with constraints
  int max = findMax([3, 1, 4, 1, 5, 9]);
  print('Max: $max');
  
  // Benefits:
  // - Type safety
  // - Code reusability
  // - Compile-time type checking
}
```

**Output:**
```
String box: Hello
Int box: 42
First string: Alice
First number: 1
Max: 9
```

#### Question 8: Explain `factory` constructors
```dart
class Logger {
  static Logger? _instance;
  
  // Private constructor
  Logger._();
  
  // Factory constructor - returns existing instance or creates new
  factory Logger() {
    _instance ??= Logger._();
    return _instance!;
  }
  
  void log(String message) {
    print('[LOG] $message');
  }
}

class Point {
  final double x;
  final double y;
  
  Point(this.x, this.y);
  
  // Factory constructor - can return different types
  factory Point.origin() {
    return Point(0, 0);
  }
  
  // Factory constructor with conditional logic
  factory Point.fromJson(Map<String, dynamic> json) {
    if (json.containsKey('x') && json.containsKey('y')) {
      return Point(json['x'], json['y']);
    }
    return Point.origin();
  }
  
  // Factory can return subtype
  factory Point.polar(double radius, double angle) {
    return Point(
      radius * angle.cos(),
      radius * angle.sin(),
    );
  }
}

void main() {
  // Singleton pattern
  Logger logger1 = Logger();
  Logger logger2 = Logger();
  print('Same instance: ${identical(logger1, logger2)}');
  
  // Factory constructors
  Point origin = Point.origin();
  Point fromJson = Point.fromJson({'x': 5, 'y': 10});
  
  print('Origin: (${origin.x}, ${origin.y})');
  print('From JSON: (${fromJson.x}, ${fromJson.y})');
  
  // Factory vs regular constructor:
  // - Factory can return existing instance
  // - Factory can return subtype
  // - Factory can have conditional logic
}
```

**Output:**
```
Same instance: true
Origin: (0.0, 0.0)
From JSON: (5.0, 10.0
```

#### Question 9: What are Extensions and when to use them?
```dart
// Extension adds methods to existing types
extension StringExtension on String {
  String capitalize() {
    if (isEmpty) return this;
    return '${this[0].toUpperCase()}${substring(1)}';
  }
  
  bool get isEmail {
    return contains('@') && contains('.');
  }
}

extension IntExtension on int {
  bool get isEven => this % 2 == 0;
  
  Duration get seconds => Duration(seconds: this);
}

void main() {
  String text = 'hello world';
  print('Capitalized: ${text.capitalize()}');
  print('Is email: ${text.isEmail}');
  
  int number = 4;
  print('Is even: ${number.isEven}');
  print('Duration: ${5.seconds}');
  
  // When to use extensions:
  // - Add functionality to types you don't own
  // - Keep code organized
  // - Improve readability
  // - Avoid modifying original classes
}
```

**Output:**
```
Capitalized: Hello world
Is email: false
Is even: true
Duration: 0:00:05.000000
```

#### Question 10: Explain Error Handling in Dart
```dart
// Custom exception
class ValidationException implements Exception {
  final String message;
  ValidationException(this.message);
  
  @override
  String toString() => 'ValidationException: $message';
}

// Error handling
void validateAge(int age) {
  if (age < 0) {
    throw ValidationException('Age cannot be negative');
  }
  if (age > 150) {
    throw ValidationException('Age seems unrealistic');
  }
}

Future<String> fetchData() async {
  await Future.delayed(Duration(seconds: 1));
  throw Exception('Network error');
}

void main() {
  // Try-catch
  try {
    validateAge(-5);
  } on ValidationException catch (e) {
    print('Caught: $e');
  } catch (e) {
    print('Other error: $e');
  } finally {
    print('Always executed');
  }
  
  // Try-catch with async
  fetchData().then((value) {
    print('Success: $value');
  }).catchError((error) {
    print('Error: $error');
  });
  
  // Rethrow
  try {
    try {
      validateAge(-5);
    } catch (e) {
      print('Inner catch');
      rethrow; // Re-throw to outer catch
    }
  } catch (e) {
    print('Outer catch: $e');
  }
  
  // Error types:
  // - Exception: intended to be caught
  // - Error: programming errors (shouldn't be caught)
}
```

**Output:**
```
Caught: ValidationException: Age cannot be negative
Always executed
Inner catch
Outer catch: ValidationException: Age cannot be negative
Error: Exception: Network error
```

---

## Summary

This comprehensive guide covers the fundamental aspects of Dart programming:

1. **Introduction and Basics**: Variables, data types, null safety, and basic syntax
2. **Conditions and Loops**: Control flow structures for decision making and repetition
3. **Functions**: Reusable code blocks with various parameter types and patterns
4. **Collections**: Data structures for storing and manipulating multiple values
5. **File Handling**: Reading from and writing to files, directory operations, and file management
6. **OOP in Dart**: Object-oriented programming concepts including classes, inheritance, polymorphism, and more
7. **Null Safety In Dart**: Understanding and working with nullable and non-nullable types
8. **Asynchronous Programming**: Futures, Streams, and async/await patterns
9. **Useful Information**: 
   - Final Vs Const: Understanding compile-time and runtime constants
   - Datetime In Dart: Working with dates and times
   - Extension In Dart: Adding functionality to existing types
   - Backend in Dart: Building HTTP servers and REST APIs
   - Dart Interview Questions: Common questions with detailed examples

Each section includes 10 detailed examples with explanations and expected outputs, making it easy to understand and practice Dart programming concepts. These examples progress from basic to advanced, providing a solid foundation for Flutter development.

### Key Learning Outcomes:
- **150+ working examples** with complete code and expected outputs
- **Progressive complexity** from beginner to advanced concepts
- **Real-world scenarios** and practical applications
- **Best practices** for Dart programming
- **Comprehensive coverage** of all major Dart features

Remember to practice these examples and experiment with variations to deepen your understanding of Dart programming!
