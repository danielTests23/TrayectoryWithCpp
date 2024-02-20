# Data types

In c++, you can choose from a variety of types of variables that are already supported in C++.

There are 4 **fundamental** data types, which are:

- [**Character**](#character-type)
- **Integer**
- **Float**
- **Boolean**

Let's go to understand how can we manage each data type and the impact in performance, because, as you saw in the [introduction](./IntroVariables.md) each variable has a storage in the memory.

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
- [Char](#char)
- [wchar_t](#wchar_t)
- [char16_t](#char16_t)
- [char32_t](#char32_t)
- [Unsigned and Signed char](#unsigned-char-and-signed-char)
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


### wchar_t

This type of char is used to represent wide characters and can be of variable size, usually 2 or 4 bytes.

**Syntax**

```cpp
wchar_t  ch2{ L'a' };
```

In this case, you'll need to use before the value the letter `L`,because it's used as a prefix for a wide character.


### char16_t

This type of char is used when you need to use 16-bit wide characters.

**Syntax**

```cpp
char16_t ch3{ u'a' };
```

In this case, you'll need to use before the value the letter `u`,because it's used as a prefix for a 16-bit wide characters.

### char32_t

This type of char is used when you need to use 32-bit wide characters.

**Syntax**

```cpp
char32_t ch3{ U'a' };
```

In this case, you'll need to use before the value the letter `U`,because it's used as a prefix for a 32-bit wide characters.


### Unsigned char and signed char

This types are very useful, because, if you are using character types as numbers signed char lend you to work in a range from -127 to 127 and the unsigned char from 0 to 255

**Syntax**
```cpp
unsigned char image[100][100];
image[0][0] = 150;  // This wont be possible with a signed char
image[1][1] = 100;
signed char pixelDifference = image[1][1] - image[0][0]; // rest with a negative value
```


