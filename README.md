# CS330 C++ Programming Project
This repo is for my CS 330 project

## History of C++

### History and Use
I have chosen to research and learn about C++. The language was created in 1979 by Bjarne Stroustrup in an effort to make a language that could help programmers make more sophisticated systems while maintaining low-level access to hardware. However, the first edition of C++ wasn't actually published until 1985. 

C++ is often used in the gaming, finance, computing, and robotics industries since it is a low-latency language. 

In game development, C++ is advantageous since it has a high performance compared to other languages. Most APIs are written in C++ to keep runtime as low as possible. Within the finance industry, C++ is used within market-making strategies in options trading since it is crucial to have low-latency programming so your data can be updated quickly and you won't be taken advantage of by a faster firm. Robotics also uses C++ as it has direct access to hardware so you can write code for sensors and other components. 

### Coding with C++

In order to code in C++, you first need to download the extension for C++ on VisualStudio Code. If you haven't installed it before, you will also need a compiler since VS Code doesn't have one. You can go to this [website](https://code.visualstudio.com/docs/languages/cpp), and install the version that is compatible with your operating system. There is an example on the website to download the necessary software for each specific OS as well as how to construct a Hello World program!

VS Code is not the only IDE that supports C++, but I chose to use it since I already had it downloaded, and I use it the most frequently for coding in other languages. Compared to programs like Python or Java, C++ runs the same way in VS Code. All you have to do is press the play button or the F5/Crtl+F5 keyboard shortcut. 
To comment in C++, all you have to do is `//` for a single line comment, or open the comment with `/*` and close it with `*/` on a different line. 

### Hello World Code

```cpp
#include <iostream>

int main() {
    std::cout << "Hello world!";
    return 0;
}
```

## Data Types and Naming Conventions

### Naming Your Variables

Naming conventions in C++ are very similar to Python. 

In C++, classes should be denoted with a capitalized first letter, and they are nouns most of the time. Uppercase letters are used as word separators, and underscores are not used. A private attribute within a class should have an 'm' added to the beginning of the name. 

Functions almost always start with a verb since they perform actions. The name should be descriptive of what the function does. The first character of the name should be lowercase, but the second word should be capitalized since functions also use uppercase letters as separators. 

Variables start with a letter of the alphabet, and numbers can only be used after that first character. The only special symbol that's allowed is the underscore. If the variable is a pointer, then a '*p' is added to the beginning. A pointer 'points' to an address of a variable. The name of a variable cannot be a keyword since that could cause issues with something being overwritten. In C++, there are 95 total keywords that you cannot name variables (a few examples are `if`, `else`, `static`, `and`, and `void`). 

Constant values are typically denoted by all capital letters. 

For example, you could use the following:

```cpp
int num = 5;
string name = 'Cindy';
double temp = 74.5;
bool fact = TRUE;

//To make a list you can use the following skeleton code
#include<list>
std::list<type> name = {value1, value2, ...};
//Here, type is the variable type (string, char, int, etc.), and name is whatever you choose to name it

//C++ doesn't use dictionaries. It uses hash maps which use the same logic
#include <map>
map <type_1, type_2> name;
//type_1 and 2 are the types of data in each part. The first is the 'key' and the second is the 'value'
```

### Notes about the C++ language

C++ is statically typed, so when you make a variable as an `int`, that cannot be changed. It is also a strong language since there is type-checking. Everything in C++ is mutable, so, instead of pointing to the same thing, an x that is assigned y actually means that you update whatever is in x with what is in y. However, you can use `const` to make something in C++ immutable.

It is useful to keep track of what kind of variables are in your program so you are aware of where things could potentially go wrong in your program!

### Operators 

You can use normal operators like `+`, `-`, `*`, `%`, and `/`. 
To decrease an integer by 1 you can use `--`, and to add use `++`.
To compare values, you can use `=`, `==`, `<`, `<=`, `>`, `>=`, and `!=`. 
The logical comparisons are `&&` for AND, `||` for OR, and `!` for NOT. 


## Making Functions in C++

### Syntax for Creating Functions

In C++, the structure for creating a function is as follows:
```
<return_datatype> function_name (<input_datatype>){
    function element;
    return something;
}
```
Looking at the above code, you can see that you have to declare the type of output of the function and what type of input it has. You can have more than 1 input if you want, and it doesn't matter the datatype. You can only return 1 item at a time, but if you need to return more you can package items together as a tuple. The example below of splitting a string into 2 parts is an example of packaging the items together in order to return both parts. 

The placement of the function in code doesn't matter since it's a compiled language. However, the function is typically placed before the main function where it is called. 

```cpp
//A function that takes in two numbers, multiplies them and returns the output
#include <iostream>
using namespace std;

int addition (int a, int b){
  int c;
  c=a*b;
  return c;
}

int main(){
  int z;
  z = addition (5,3);
  cout << "The result is " << z;
}

```

### Recursion

C++ does support recursive functions, and you can create one by calling the function again with the updated value. An example of using recursion to calculate a factorial is shown below. 

```cpp
// A recursive function calculating a factorial
#include <iostream>
using namespace std;

int factorial(int a){
  if (a > 1)
   return (a * factorial (a-1));
  else
   return 1;
}

int main1(){
  int number = 9;
  cout << number << "! = " << factorial (number);
  return 0;
}
```

### String Splitting

```cpp
//A function that takes in a string and splits it into two strings, then returns both strings
#include <iostream>
#include <string>
#include <utility>

std::pair<std::string, std::string> splitString(const std::string& inputString) {
    std::pair<std::string, std::string> result;

    // Calculate the midpoint to split the string into two parts
    int midpoint = inputString.length() / 2;

    result.first = inputString.substr(0, midpoint);
    result.second = inputString.substr(midpoint);
    return result;}

int main() {
    std::string input;

    std::cout << "Enter a string: ";
    std::cin >> input;
    
    // Split the string
    std::pair<std::string, std::string> splitted = splitString(input);

    // Output the two split strings
    std::cout << "First part: " << splitted.first << std::endl;
    std::cout << "Second part: " << splitted.second << std::endl;

    return 0;}
```

### Pass-by-Value/Reference

```
#include <iostream>

// Function to test pass-by-value or pass-by-reference
void testFunction(int value, int& reference) {
    value = 100;        // Modifying the value parameter
    reference = 200;    // Modifying the reference parameter
}

int main() {
    int val = 50;
    int ref = 50;

    std::cout << "Before function call: val = " << val << ", ref = " << ref << std::endl;

    testFunction(val, ref);

    std::cout << "After function call: val = " << val << ", ref = " << ref << std::endl;

    return 0;
}
```
The function above demonstrates that C++ is pass-by-reference since when the reference variable is changed in the function, the reference is updated while the value is not. 

In C++, things are stored on the stack unless it is specified as `new`. For example, `int var` would make the variable `var` stored on the stack, while `int* ptr = new int` would make the variable and store it on the heap. 

### Scoping Rules

 1. Variables declared outside of functions or a class have global scope.
 2. Variables made within a code block `{}` only have local scope. Outside of that block they do not exist and cannot be called.
 3. Items made within a function only exist inside that function, and, unless they are returned, you cannot see them outside of that.

C++ is statically scoped based on the rules above. 

C++ does not inherently prevent any side-effects since one of the goals of the language is to provide enough flexibility to the user. To prevent any unwanted side-effects, you should make sure that the scoping is correct so variables are not changed without you meaning them to be altered. 

## Selection, Loops, and Conditionals

A basic example of an if/else statement is shown below. As you can see, the boolean to pass the if is `true`. To make an else if statement, you can add a section for `else if` with the same syntax as the first if statement. Inside each if/else if/ else section, you delimit the code inside with `{}`. However, you do not need a delimiter (this can lead to the 'dangling else' problem that will be discussed later. 
```
#include <iostream>

int main() {
    bool x = true;

    if x {
        cout << "x is true!" << endl;
    \\else if ...
    } else {
        cout << "x is not true!" << endl;
    }

    return 0;
}
```
To include 2 conditions in the statement, you can use either `&&` for 'and', `||` for 'or', `!` for 'not', and `==` for 'equals'. The following code shows how to use these statements!
```
#include <iostream>

int main() {
    int x = 5;
    int y = 10;

    if x == 5 && y == 10 {
        cout << "Yes" << endl;
    else if  x == 0 {
        break
    } else {
        cout << "x and y aren't right" << endl;
    }

    return 0;
}
```

C++ does use short-circuit evaluation based on the following example:
```
bool a = false;
bool b = true;

if (a && b) {
    // This code will not execute because a is false and won't evaluate b
}
```

We can see that C++ just stops after evaluating the first condition. 

As mentioned above, it is not necessary for an if/else statement to include brackets. This can save time if the statement is already simple, but it could cause problems if you have nested statements since the else statement might run at an unwanted time. 

C++ also supports switch statements for various cases you want to test for. The skeleton code for it is shown below

```
switch (expression) {
    case constant1:
        // code to be executed if expression equals constant1
        break;
    case constant2:
        // code to be executed if expression equals constant2
        break;
    default:
        // code to be executed if none of the cases match the expression
}
```
The only limitation for this is that you cannot add `continue` to get all the statements to be evaluated. 


## Classes and Inheritance

C++ is an object-oriented language, meaning that it primarily uses classes and calls those objects to perform functions. The following code is a basic example of how to make a class and which functions are commonly used in classes. In this example, a `Person` object is made with name and age as its attributes. 

```
#include <iostream>
#include <string>
using namespace std;

class Person {
//this creates the attributes of the class. Here, these 2 variables are private.
private:
    string name;
    int age;

public:
    // Constructor to initialize name and age
    Person(string personName, int personAge) : name(personName), age(personAge) {}

    // Function to set the name. Void is included since nothing is returned in this set function. Only the name is set.
    void setName(string personName) {
        name = personName;
    }

    // Function to set the age. Again, nothing is returned so void is used. 
    void setAge(int personAge) {
        age = personAge;
    }

    // Function to get the name. Since the name is a string, you need to specify the type of return you expect.
    string getName() const {
        return name;
    }

    // Function to get the age. Int is added since age is an integer.
    int getAge() const {
        return age;
    }
};

int main() {
    // Creating a Person object
    Person person("Alice", 30);

    // Accessing and displaying person's details
    cout << "Initial Details:" << endl;
    cout << "Name: " << person.getName() << endl;
    cout << "Age: " << person.getAge() << endl;

    // Modifying person's details
    person.setName("Bob");
    person.setAge(25);

    // Displaying modified details
    cout << "\nModified Details:" << endl;
    cout << "Name: " << person.getName() << endl;
    cout << "Age: " << person.getAge() << endl;

    return 0;
}
```

One important aspect to be aware of is that C++ does not have a built-in toString() method. This means you cannot simply use `cout<< object_name << endl;` to print out an object. In order to do this, you need to create either your own toString() method by using one of the following: 

```
string toString() const {
        std::ostringstream strout;
        strout << "object: " << object;
        return strout.str();
}
// or you can overwrite the << operator

// the keyword friend is used to overwrite a operator
friend std::ostream& operator<<(std::ostream& os, const Trade& trade) {
        os << "Object: " << object.attribute << endl;
        return os;
    }
```


### Inheritance

To inherit an object and apply it to a new class, you can use `accessSpecifier` which *specifies* whether the base class that a derived class will use private or public attributes. You can see an example of the syntax of this below. If you use `public` as the accessSpecifier, you inherit the public aspects of base class as public aspects of the derived class. If you instead use `private`, all the variables (no matter if they are public or not) will be inherited as private attributes. 

```
class BaseClass {
    // Base class definition
};

class DerivedClass : accessSpecifier BaseClass {
    // Derived class definition
};
```



Resources: https://unstop.com/blog/history-of-cpp

https://www.geeksforgeeks.org/history-of-c/

https://learn.microsoft.com/en-us/cpp/cpp/comments-cpp?view=msvc-170




