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
