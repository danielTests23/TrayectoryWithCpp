# Data types

In c++, you can choose from a variety of types of variables that are already supported in C++.

There are 4 **fundamental** data types, which are:

- [**Character**](#character-type)
- [**Integer**](#int-type)
- **Float**
- **Boolean**

Let's go to understand how can we manage each data type and the impact in performance, because, as you saw in the [introduction](./IntroVariables.md) each variable has a storage in the memory.

> [!IMPORTANT]  
> Each data type is going to include the minimum size that is going to take in your system, if you verify the sizes through sizeof function, you could not get the same size, this can variate for a lot of reasons (version of compiler, os, processor). If you want to know why this happens, checks this [conversation](https://stackoverflow.com/questions/1240121/sizeofint-sizeoflong-sizeoflong-long-always-true), and this [example](https://www.intel.com/content/www/us/en/developer/articles/technical/size-of-long-integer-type-on-different-architecture-and-os.html) of a case of long.

# Character type.

This data type just represent a single character, you can store in this type of variable a letter like 'W' or symbols as "#".

**Example:**

```cpp
char letter {'a'};
```

#### ASCII values

I'll be updating this guide and show you what is the ASCII table and it's functionality in this [section](../../generalKnowledge/), meanwhile, you can check what is in this [link](https://en.wikipedia.org/wiki/ASCII)

- ASCII Range of ‘a’ to ‘z’ =  97-122

- ASCII Range of ‘A’ to ‘Z’ =  65-90

- ASCII Range of ‘0’ to ‘9’ = 48-57


## Types of char

Char has 4 different types that are differenced for the size in memory that the variables can store. Any of these types can use [UNICODE](https://www.unicode.org/standard/WhatIsUnicode.html).

This are the 4 types of char, you can check it below:
- [**Char**](#char)
- [**wchar_t**](#wchar_t)
- [**char16_t**](#char16_t)
- [**char32_t**](#char32_t)
- [**Unsigned and Signed char**](#unsigned-char-and-signed-char)
---

### Char 
> Size: 1 byte in size. (8 bits)

This is the standard declaration of this type, so you'll see this syntax in most programs for it's popularity and standard.

**Syntax**

```cpp
char d {'d'};
```

Also, as you saw in the [ASCII](#ascii-values) section, you can convert a char to it's numerical value, in this way:

```cpp
char d {'g'};
int translation {int(d)};
//the value of translation is 103, which is the equivalent of g in ASCII
```

If you want to transform now the value of a number to a char, you can do it in this way:

```cpp
int d {103};
char translation {char(d)};
//The output will be 'g', which is the equivalent of 103 in ascii
```

> [!TIP]
> Remember to always have an [ASCII table](https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fwww.alpharithms.com%2Fwp-content%2Fuploads%2F340%2Fascii-table-alpharithms-2048x1220.jpg&f=1&nofb=1&ipt=4d4eae3d8d341d81242019cc85c99f76a4b2cf3a720bb80dd63d8d9fa3e1bdec&ipo=images) in other window to check the conversion and try it yourself.

**More Examples**
- [Creation of a char](./Scripts/charExample.cpp)
- [Conversion of a char](./Scripts/charConversionExample.cpp)

---

### wchar_t
> Size: In practice, it is 32 bits and holds UTF-32 on Linux and many other non-Windows systems, but 16 bits and holds UTF-16 code units on Windows. Can represent the largest supported character set.

This type of char is used to represent wide characters and can be of variable size, usually 2 or 4 bytes.

**Syntax**

```cpp
wchar_t  ch2{ L'a' };
```

In this case, you'll need to use before the value the letter `L`,because it's used as a prefix for a wide character.

---

### char16_t
> Size: 2 bytes in size. (16 bits)

This type of char is used when you need to use 16-bit wide characters.

**Syntax**

```cpp
char16_t ch3{ u'a' };
```

In this case, you'll need to use before the value the letter `u`,because it's used as a prefix for a 16-bit wide characters.

---

### char32_t
> Size: 4 bytes in size. (32 bits)

This type of char is used when you need to use 32-bit wide characters.

**Syntax**

```cpp
char32_t ch3{ U'a' };
```

In this case, you'll need to use before the value the letter `U`,because it's used as a prefix for a 32-bit wide characters.

---

### Unsigned char and signed char
> Size: 1 byte at least. (8 bits)

This types are very useful, because, if you are using character types as numbers signed char lend you to work in a range from -127 to 127 and the unsigned char from 0 to 255

**Syntax**
```cpp
unsigned char image[100][100];
image[0][0] = 150;  // This wont be possible with a signed char
image[1][1] = 100;
signed char pixelDifference = image[1][1] - image[0][0]; // rest with a negative valuem
```

# Int type

This is a type of data that just can store integer values, such as 23 or 7.

**Example:**

```cpp
int value {1};
```

## Types of int

Int has 2 different types that allow different ranges of data:

- [Signed int]()
- [Unsigned int]()

### Signed Int

A numeric data that can store positive and negative values, in an standard OS, you can store from -2^32/2 – 1 (-2147483648) to 2^32/2 – 1 ( 2147483647 ). If you have lower or higher values than this ones, you'll get an overflow error.


### Unsigned Int

A numeric data that can store only positive values, in an standard OS, you can store from 0 to 2^32 -1 ( 4294967295 ). It wraps arounds 0 if the value exceeds the maximum limit.

In both types of int exists more types, as the following:

- [**short int**](#short-int)
- [**int**](#int)
- [**long int**](#long-int)
- [**long long int**](#long-long-int)

The unique difference between both, is the ranges of values that can cover 


### short int

> Size: 2 bytes (16 bits)

Is the most basic representation of this value, you can store integer values in the range from -32,767 to 32,767 (signed int) and from 0 to 65,535 (unsigned int)


**Syntax**
```cpp
short int x {1};
```

### Int

> Size: 2 bytes at least (16 bits). 

This type can take at least the value of short, but also, can increment it's value depending on a lot of variables, normally in all systems reaches 4 bytes (8 bits). This ranges from -2147483648 to 2147483648 (signed value).

**Syntax**
```cpp
int x {1};
```

### long int
> Size: 4 bytes at least (32 bits). 

This types take at least 4 bytes, but as the int type, can take more memory and increment it's size to 8 bytes normally, it's range in this case is from -9223372036854775807 to 9223372036854775807 (signed value)

**Syntax**
```cpp
long int x{1};
```

### long long int

> Size: 8 bytes at least (64 bits). 

This type takes at least 8 bytes. It can take from -9223372036854775808 to 9223372036854775808 (signed value), it's the largest size of this types

**Syntax**
```cpp
long long int x{1};
```


**References**
- [cppReference](https://en.cppreference.com/w/cpp/language/types)
- [cplusplus](https://cplusplus.com/doc/tutorial/variables/)
- [geeksforgeeks](https://www.geeksforgeeks.org/difference-between-unsigned-int-and-signed-int-in-c/)
- [microsoft](https://learn.microsoft.com/en-us/cpp/cpp/fundamental-types-cpp?view=msvc-170)