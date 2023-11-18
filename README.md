# CS330 C++ Programming Project
This repo is for my CS 330 project

## Assignment 1:

### History and Use
I have chosen to research and learn about C++. The language was created in 1979 by Bjarne Stroustrup in an effort to make a language that could help programmers make more sophisticated systems while maintaining low-level access to hardware. However, the first edition of C++ wasn't actually published until 1985. 

C++ is often used in the gaming, finance, computing, and robotics industries since it is a low-latency language. 

In game development, C++ is advantageous since it has a high performance compared to other languages. Most APIs are written in C++ to keep runtime as low as possible. Within the finance industry, C++ is used within market-making strategies in options trading since it is crucial to have low-latency programming so your data can be updated quickly and you won't be taken advantage of by a faster firm. Robotics also uses C++ as it has direct access to hardware so you can write code for sensors and other components. 

### Coding with C++

In order to code in C++, you first need to download the extension for C++ on VisualStudio Code. If you haven't installed it before, you will also need a compiler since VS Code doesn't have one. You can go to this [website](https://code.visualstudio.com/docs/languages/cpp), and install the version that is compatible with your operating system. There is an example on the site to download the necessary software for each specific OS as well as how to construct a Hello World program!

VS Code is not the only IDE that supports C++, but I chose to use it since I already had it downloaded, and I use it the most frequently for coding in other languages. Compared to programs like Python or Java, C++ runs the same way in VS Code. All you have to do is press the play button or the F5/Crtl+F5 keyboard shortcut. 
To comment in C++, all you have to do is `//` for a single line comment, or open the comment with `/*` and close it with `*/` on a different line. 

Resources: https://unstop.com/blog/history-of-cpp

https://www.geeksforgeeks.org/history-of-c/

https://learn.microsoft.com/en-us/cpp/cpp/comments-cpp?view=msvc-170

### Hello World Code

```cpp
#include <iostream>

int main() {
    std::cout << "Hello world!";
    return 0;
}
```

## Assignments 2

### Naming Conventions

Naming conventions in C++ are very similar to Python. 

In C++, classes should be denoted with a capitalized first letter, and they are nouns most of the time. Uppercase letters are used as word separators, and underscores are not used. A private attribute within a class should have an 'm' added to the beginning of the name. 

Functions almost always start with a verb since they perform actions. The name should be descriptive of what the function does. The first character of the name should be lowercase, but the second word should be capitalized since functions also use uppercase letters as separators. 

Variables start with a letter of the alphabet, and numbers can only be used after that first character. The only special symbol that's allowed is the underscore. If the variable is a pointer, then a '*p' is added to the beginning. A pointer 'points' to an address of a variable. The name of a variable cannot be a keyword since that could cause issues with something being overwritten. In C++, there are 95 total keywords that you cannot name variables (a few examples are `if`, `else`, `static`, `and`, `void`). 

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

#### Operators 

You can use normal operators like `+`, `-`, `*`, `%`, and `/`. 
To decrease an integer by 1 you can use `--`, and to add use `++`.
To compare values, you can use `=`, `==`, `<`, `<=`, `>`, `>=`, and `!=`. 
The logical comparisons are `&&` for AND, `||` for OR, and `!` for NOT. 


## Assignment 3

### Functions

```cpp
//Write a function that takes in two numbers, multiplies them, and returns the output
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

```cpp
// Write a recursive function (one that calculates a factorial is fine)
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

```cpp
//Write a function that takes in a string (or your language's equivalent) and splits it into two strings, then returns both strings
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













