# Functions in C++
### A Function is a reusable block of code designed to perform a specific task. It helps break large programs into smaller, logical parts. Functions make code cleaner, easier to understand, and more maintainable.

### Just like in other languages, C++ functions can take inputs (called parameters), execute a block of statements, and optionally return a result. C++ also supports advanced features like function overloading, default arguments, and inline functions, which give more flexibility compared to C.

# Function Overloading in C++
### Function overloading allows us to define multiple functions with the same name but different parameters. It is a form of compile time polymorphism in which different functions with same name can perform different jobs based on the different parameters passed.
### -> Avoids name conflicts and unnecessary function names
### -> Makes the code easy to understand and making user friendly as the same meaningful function name is used for different types of inputs.

```c
#include <iostream>
using namespace std;

int add(int a, int b) {
    return a + b;
}
int add(int a, int b, int c) {
    return a + b + c;
}

int main() {
    int a = 5, b =7, c = 11;
    cout << add(a, b) << endl;
    cout << add(a, b, c);

    return 0;
}
```
# Different Ways of Function Overloading
## A function in C++ can be overloaded in three different ways:

### -> By having different number of parameters.
### -> By having different types of parameters.
### -> By having both different number and types of parameters.

## Different Number of Parameters
### We can overload a function by changing the number of parameters that it accepts
```c
#include <iostream>
using namespace std;

int multiply(int a, int b);
int multiply(int a, int b, int c);

int main()
{
    cout << multiply(10, 2) << endl;
    cout << multiply(5, 6, 4);

    return 0;
}

int multiply(int a, int b) {
    return a * b;
}
int multiply(int a, int b, int c) {
    return a * b * c;
}
```
# Different Types of Parameters
### We can also change the data type of the parameters while keeping the same function name in function overloading.

```c
#include <iostream>
using namespace std;

int add(int a, int b);
double add(double a, double b);

int main()
{
    
    cout << add(10, 2) << endl;
    cout << add(5.3, 6.2);

    return 0;
}

int add(int a, int b) {
    return a + b;
}
double add (double a, double b) {
    return a + b;
}
```
# Different Number and Types of Parameters
### Functions can also be overloaded by changing both the number and types of parameters.
```c
#include<iostream>
using namespace std;

int add(int a, double b);
double add(double a, int b, int c);

int main()
{

    cout << add(10, 2.5) << endl;
    cout << add(5.5, 6, 12);
    return 0;
}

int add(int a, double b) { 
    return a + (double)b;
}  
double add(double a, int b, int c) {
    return a + (double)b + (double)c;
}
```
# Functions that Cannot be Overloaded
### -> Functions with same parameter but different passing method (i.e. passed by value and passed by reference).
### -> Member function declarations with different access specifier but same name and same parameter-type-list cannotbe overloaded.
### -> Functions with different return type can not be overloaded
```c
#include <iostream>
using namespace std;

// Changing return type only
string get() {
    return "This returns string";
}
int get() {
    return 99;
}

int main() {

    // Calling the function even with specifying
    // the type of return value we want
    string s = get()
    cout << s;
    
    return 0;
}
```

# Default Arguments in C++
### A default argument is a value provided for a parameter in a function declaration that is automatically assigned by the compiler if no value is provided for those parameters in function.
### -> Default arguments must be present on the right side only. Once a default argument is provided, all the arguments to its right must also be defaults.
```c
#include <iostream>
using namespace std;

void f(int a = 10)
{
    cout << a << endl;
}

int main()
{
    f();

    f(221);

    return 0;
}
```
# Rules to Follow
### There are some important rules and best practices to keep in mind when using default arguments in C++:
## 1. Default Values Should be Specified in Function Declarations
### The default values for parameters should be specified in the function declaration (or prototype). If a function is declared and defined separately, the default values must be in the declaration, not in definition.
```c
// Declaration with default argument
void func(int x = 10);

// Definition without default argument
void func(int x)
{
    cout << "Value: " << x << endl;
}
```
## 2. Default Arguments Cannot Be Modified
### Once default arguments are defined in the declaration, they cannot be modified in the function definition. If you try to change the default value in the definition, it will result in a compilation error.
```c
// Declaration
void f(int a = 10);

// This definintion will throw and error
void f(int a = 222)
{
    // statements
}
```
## 3. Default Arguments Must Be Provided from Right to Left
### In a function with multiple parameters, default values must be provided from the rightmost parameter to the left. It means that if a parameter has a default argument, all parameters to its right must also have default values.
```c
// Valid
void func(int x, int y = 20);

// Invalid, as `y` does not have a default value
void func(int x = 10, int y);
```
### Example :
```c
#include <iostream>
using namespace std;

// Function with default height 'h' argument
double calcArea(double l, double h = 10.0)
{
    return l * h;
}

int main()
{
    cout << "Area 1:  " << calcArea(5) << endl;

    cout << "Area 2: " << calcArea(5, 9);
    return 0;
}
```

