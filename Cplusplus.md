# C++ and CS 308
**This file's gonna tell you about the journey I have learned C++ in class CS 308 at Fulbright**

## Table of Contents
- [History of C++](#history-of-C++)
- [Getting started](#getting-started)
- [Names, Types and Binding](#Names-types-and-inding)
- [Selection Control Structures](#selection-control-structures)
- [Loops and Subroutines](#loops-and-subroutines)
- [Object and Classes](#object-and-classes)
- [Reference](#reference)

<h1>History of C++ </h1>
C++ was created in 1985 by Bjarne Stroustrup. It was written as an extension of C programming language. C++ is a multi-purpose programming language, which is applied in desktop applications (Adobe systems such as Illustrator, Photoshop,..), video games (CSGO, League of Legends, PUBG, Call of Duty), servers core of e-commerse, web search or databases (Firstfox, google applications, MySQL) and performance-critical applications such as operating Systems (Apple OS, Microsoft Windows OS), banking applications (Infosys Finacle)
<br>
<br>
<h1>Getting started </h1>
To install C++, we need to have an IDE that have our langugae package. In my case, I choose Visual studio which has package C/C++. Then I need to install the compiler for C ++ named **msys2** so that I we can run C++ on our device.
C++ has another recommended IDE that is Visual Studio, but due to some reasons I could not run HelloWorld on this IDE. Therefore I have chosen Visual studio which is more familiar to me as an IDE. 
<br>
To run program in C++, we just need to write program which has the header (#include <iostream>) and main component (int main()) then run it by the key combination **Crtl + Alt + N**. 
<br>
For example:
<br>
	
```
	
#include <iostream>
int main()
{
	std::cout << "Hello, World!" << std::endl;
	return 0;
}
```
<br>
<br>
	<h1>Names, Types and Binding</h1>
C++ has 44 keywords and 95 reserved words.
<br><br>
 C++ naming requirements for variables are:
	
 - Must be identified with unique names aka identifiers.	
 - It can be short names (a, b, c,...) or more descriptive names like (gender, school, studentNumber)	
 - It can contain letters, digits and underscores
 - It must begin with a letter or an underscore
 - It is case sensitive
 - It can not contain whitespaces or special character
 - It can not be reserved words
 C++ uses CamelCase for naming conventions
 The class name should be a noun meanwhile method and function name should begin with a verb

 It is mainly standard of community but there is also some conventions enforced by the compiler:
 - The first character in the class name must be upper case.
 - No underscores are permitted in the class name.

C++ is a statically, weakly and explicitly typed language
<br><br>
In c++, except for constant is immutable all other objects are mutable in c++.	
<br><br>
Mixed type operations are allowed in C++. When a variable does not have the same type as the result of the operation, the value of the variables is converted to the tye of the result and the operation is performed.
<br><br>
We can use mixed-type operations in c++. Due to that, the type of result maybe changes differently from the type of operation. Besides that, we cannot store different types in lists and convert between data types.
<br>
<br>
Identifier names and operator symbols bound in early binding process meanwhile virtual function bound in late-binding process.
<br><br>
In c++, we also have a pointer which is used to point to the address of the variable allocate.	
	
<br>
<br>
	<h1> Selections Control Structure </h1>
The boolean value in C++: true and false | 1 and 0
<br><br>
The type of conditional statements are available in C++:
- if/ else
- if/ else if/ else 
- Switch
<br><br>

In C++, the code block is delimited under each condition in the selection control statement by moving from one to another code depending on whether a particular condition is sastified or not.
<br><br>
C++ supports short-circuit evaluation 
<br>
Example:

```
int u = -3, i = 10;
if(u>0 && i >0){
        std::cout << "both two numbers are bigger than zero" << endl;
    }
```
	
For "dangling else", C++ will prioritize counting the else for the inner if for example we have the below code:
	
```
int a = 5, b=7, c=7;
    if (a>5)
    if(b>6){
        std::cout << "alo";
    }else{
        std::cout << "olo";
    }
```

Because the else statement is counted for the inner if then the result to cout is nothing because the if condition (a>5) failed without any else statement. 	
<br><br>
C++ also supports switch or case statement. In c++ we need to use break to get out of switch or case statements. And we are also able to use “continue” to have all of the conditions evaluated.
<br>
Example: 

```switch (something)
    {
    case A:
    case B:
        break;
    default:
        // get another something and try again
        continue;
    }
    // do something for a handled something
    do_something();
```

**The below example demonstrates all the mentioned parts about selection control structures in C++**

```
#include <iostream>
using std::endl;
int main(){
    //a one-condition if/else statement (i.e. "if x == true")

    bool x = true;
    if(x==true){
        std::cout << "True" << endl;
    };
    //a multi-condition if/else statement (i.e. "if x>0 && y< 10)

    int a = 3, b = 10;
    if(a>0 && b <20){
        std::cout << a + b << endl;
    }
    //if/elif/else statements
    int z = 6;
    if(z>3){
        std::cout << "z is bigger than 3" << endl;
    }else if (z<3){
        std::cout << "z is smaller than 3" << endl;
    }else {
        std::cout << "z is equal 3" << endl;
    }
    //short-circuit logic
    int u = -3, i = 10;
    if(u>0 && i >0){
        std::cout << "both two numbers are bigger than zero" << endl;
    }
    if(u>0 || i >0){
        std::cout << "there is at least one number bigger than 0" << endl;
    }
    //a switch-case statement
    int s=10;
    switch(s){
    case 0:
        std::cout << "bad" << endl;
        break;
    case 5:
        std::cout << "moderate" << endl;
        break;
    case 10:
        std::cout << "excellent" << endl;
        break;
    default:
        std::cout << "Point" <<endl;
        break;
    }


    return 0;
}
```	
<br><br>
	<h1> Loops and Subroutines </h1>

C++ inlcude many multipe types of loops:
-	While: when the specified condition is reached, the while loop will execute a block of code until the condition is not sastified.
	
```
while (condition) {
  // code block to be executed
}
```

-	Do/ while: the loop will execute the code block once then checking if the condtion is sastified or not and repeat the loop if true.

```
do {
  // code block to be executed
}
```
	
while (condition);
-	For: for exactly n times defined in the for statement, the code block will be executed by the for loop.

```
for (statement 1; statement 2; statement 3) {
  // code block to be executed
}
```

-	Foreach: different from for loop that will execute the loop n times, foreach will execute the code block for each elements of an array 

```
int arr = {1,2,3}
for (int i: arr){
// code block to be executed
}
```
<br>
And the syntax for declaring a function in C++

```
dataType functionName(parameter1, parameter2){
// code block to be executed
}
```
	
<br>
There are some rules about where the function has to be placed in C++ so that it can run: C++ require to place the function properly to run it, particulalrly, we need to declared the function before calling the function name.
<br><br>
C++ also supports recursive functions. And here is an example of recursive functions in C++ that calculate the factorial of number a.

```
int factorial (int a){
    if(a>0){
        return a*factorial(a-1);
    }
    else{
        return 1;
    }
}
```
<br>
C++ can accept multiple parameters. And it can also be of different data types. 
<br>For example the following functions is runnable: 

```
void test(int a, string b){
    cout<<a<<b;
}
```
<br>

C++ can not return multiple values at the same time.
But we can make many unofficial way to implement it. For example: ```using std:: pair, std::tuple``` to return multiple values or adding multiple values into one String and return that string.
<br><br>
**Below is an example program summarizing all mentions parts**

```
	#include <iostream>
#include <string>
using namespace std;

int multiplier(int a, int b)
{
    return a * b;
}
int factorial (int a){
    if(a>0){
        return a*factorial(a-1);
    }
    else{
        return 1;
    }

}
int plus1 (int a){
    a = a + 1;
    return a;
}
string stringSplitter( string str){
    string str1, str2;
    for(int i = 0; i<(int)str.size()/2; i++){
        str1 += str[i];
        str2 += str[str.size()/2+i];
    }
    return (string)"String 1: " + str1 + (string)" String 2: " + str2;
}

int main()
{
    int i = 5;
    int j =10;
    int arr[] = {5, 6, 7, 8, 9};
    string str = "abcdef";
    int temp;
    int value = 5;
    cout<<"While"<<endl;
    while (i<10){
        cout<<i<<endl;
        i = i+1;
    }
    cout<<endl;
    cout<<"Do/While"<<endl;
    do{
        cout<<j<<endl;
        j = j-1;
    }
    while (j>5);
    cout<<"For"<<endl;
    for (int k = 0; k < 5; k++) {
        cout << k << endl;
    }
    cout<<endl;
    cout<<"Foreach"<<endl;
    for(int l: arr){
        cout<<l<<endl;
    }
    cout<<endl;

    cout<<"A function that takes in two numbers, multiplies them, and returns the output"<<endl;
    cout<<multiplier(5,6)<<endl;
    cout<<endl;

    cout<<"A recursive function"<<endl;
    cout<<factorial(12)<<endl;
    cout<<endl;

    cout<<"A function that takes in a string and splits it into two strings, then returns both strings"<<endl;
    cout<<stringSplitter(str)<<endl;
    cout<<endl;

    cout<<"Call your functions and save the results of the function calls in variables"<<endl;
    temp = factorial(12);
    cout<<temp<<endl;
    cout<<endl;

    cout<<"a function that tests whether my language is pass-by-reference or pass-by-value."<<endl;
    plus1(value);
    if (value == plus1(value)){
        cout<<"C++ is passing by reference by default"<<endl;
    }else{
        cout<<"C++ is passing by value by default"<<endl;
    }
    return 0;
}
```
<br><br>
	<h1> Objects and Classes</h1>
C++ is an object- programming language so it does have classes or objects.
<br><br>
To create a class, we declare the class as below

```
class RandomClass {
	// define attributes or method
}
```

<br>
There are some naming convention for declaring a class: it shoul be a noun and is written in **CamelCase** which starts with a capital letter and including no special characters even `_`

<br><br>
In C++, an object is created from a class. To create an object, we scpecify a class name, followd by the object name and to use the class attributes, we use `.` on the object.
<br><br>
For example:
<br>

```
class RandomClass{
	public:
		string randomWorld;
}
int main(){
	RandomClass randomObject;
	randomObject.randomWorld;
}
```

<br><br>
	Methods are the functions that belongs to a class and it can be:
	- Inside class definition
	- Outside class definition
<br><br>
For example, method `randomMethod`:
<br>
```
class RandomClass{
	public:
		void randomMethod() {
			cout << "Random random random";
		}
};
```
	
C++ has standard methods for functions that serve a similar purpose accross all objects, which is called libray functions or built-in functions. By using built-in functions, we do not need to write the functions by urselves because we can directly these functions right in our code.
<br><br>
There are some common built in functions, that are: strlen() return the length of a string, sqrt() return the square root of a number or pow() return the power result of a number by powering with other number.
<br><br>
C++ allows both single and multiple inheritance, which can be grouped in two categories:
	- derived class (child)
	- base class (parent)
To inherit a class, we use `:` symbol
<br><br>
For example class car inherits class vehicle:
<br>
```
class Vehicle {
	...
}
class Car: public Vehicle {
	...
}
```
<br><br>
	<h1>References</h1>
- [W3schools C++ Tutorial](https://www.w3schools.com/CPP/default.asp)
- [Learn Cpp](https://www.learncpp.com/)
- [Programiz Cpp](https://www.programiz.com/cpp-programming)
- [Tutorialspoints Cplusplus] (https://www.tutorialspoint.com/cplusplus/index.htm)
- [Cplusplus tutorial](https://www.cplusplus.com/doc/tutorial/)
