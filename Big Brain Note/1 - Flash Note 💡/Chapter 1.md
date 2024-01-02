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


## Implicit Promotion
Unary and binary promotion are mechanisms in C++ that automatically convert smaller or lower-ranked types to larger or higher-ranked types to ensure consistency during certain operations.

## Operators Precedence
- Unary > Binary
- math > comparison > bitwise > logic > compound assignment > comma
## Comma Operator
- if there is a comma, then return the value of the right 
```C++
int x = (3,4); // x = 4
int y; // y = 5
int z;
z = y,x; // z = 4
```

## Spaceship Operator (<=>)
Allow comparing two objects in a similar way of `strcmp`
- Can greatly simplify the comparison operators overloading

## Fixed Width Integers : it's better to use it.
- have the same size on any architecture
`int8_t` , `uint8_t`
`int16_t` , `uint16_t`
`int32_t` , `uint32_t`
`int64_t` , `uint64_t`
- I/O stream interprets `uint8_t` and `int8_t` as char and not as integer values
- `size_t` , `ptrdiff_t` data types for storing the biggest representable value on the current architecture
- `size_t` 
	- an unsigned integer type (of at least 16-bit)
	- the return type of `sizeof()`
	- used for size measures
- `ptrdiff_t` 
	- singed version of `size_t` for computing pointer difference
### Overflow & Wraparound
- Overflow
	- the res of the arithmetic operation exceeds the word length
- Wraparounf
	- The res of the arithmetic operation is reduced modulo 2^N, where N is the number of bits of the word
## Singed Integer  VS Unsigned Integer
| Signed Integer                                       | Unsigned Integer                     |
| ---------------------------------------------------- | ------------------------------------ |
| positive, negative, zero                             | only non-negative values             |
| negative values (2^31-1 ) more than positive(2^31-2) | Discontinuity in 0, 2^32-1           |
| Overflow / Underflow -> undefined behavior           | Wraparound -> well-defined           |
| Bit-wise operations are implementation defined       | Bit-wise operations are well-defined |

- Time to use Signed Integer
  1. If it can be mixed with negative values
  2. expressing non-negative values with signed integer and assertions
  3. exploit undefined behavior in loops
- Time to use Unsigned Integer
  1. If the quantity can never be mixed with negative values
  2. bitmask values
  3. division, modulo
  4. safety-critical system. signed integer overflow could be "non determinisitc"
smaller type to larger type will keep the sign
```c++
int16_t x = -1;
int y = x;
cout << y // -1
```

larger typer to smaller type will modulo to the number of bits of the smaller type
```c++
int x = 65537 // which in greater then 2^16 (65536) 16 bits
int16_t y = x;
cout y; // 1 since 65537%2^16
```
