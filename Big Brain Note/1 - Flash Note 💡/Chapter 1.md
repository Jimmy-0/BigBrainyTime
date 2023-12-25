```c++
#include<iostream>
int main(){
	std:: cout<<"hello";
}
```
`cout` : represent the standard output stream
`std::cout` : data is directed to a destination, which is the standard output
```c++
#include<iostream>
using namespace std;
int main(){
	cout <<"hello";
}
```
using `namespace std`  m can omit the std

## Why using iostream?
1. no `%` needed in iostream ! -> reduce the error compare to C
2. allow user defined types to be passed to I/O stream

# Type
## integers
## floating points

## void
- Represents absence of type; commonly used as a return type for functions that do not return a value.
- if a void in a function
	- void f() -> no return type
	- f(void) -> no parameters
## `nullptr`
- A keyword representing a null pointer; used in modern C++ instead of `NULL` or `0` for pointers.

