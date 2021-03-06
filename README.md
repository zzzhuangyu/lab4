# EECS 230 Lab 4

In this lab, you will learn about `struct`s and `class`es in C++.

## Introduction to `struct`s and `class`es

`struct`s and `class`es are user-defined types. They are used to abstract higher-level concepts representing domain knowledge. Thus, they are used to characterize a certain "thing" in a program. They can be used to represent abstract concepts of data, such as a certain piece of data. For instance, an MP3 file could be represented as a `class`, holding the following information: a Tag and Audio. The Tag could be represented as a `class`, containing the following data as `string`s: Name, Artist, Album, Genre, etc. The Audio could be represented as a `class`, containing the audio as a two-dimensional matrix of `double`s representing time and amplitude.

We will focus on `struct`s in this lab because `class`es have some intricacies regarding access control, meaning that certain data inside a `class` can be protected or hidden from other parts of a program. A `struct` has all of its data public, meaning that everything can access the data inside a variable of the `struct` type.

The following shows the declaration of a `struct` representing a date:
```
struct Date {
    int year;
    int month;
    int day;
    bool is_AD;
};
```
As shown, a `struct` can have multiple data types as members. To declare a variable of the `Date` type and set its data:
```
    Date today;
    today.year = 2016;
    today.month = 1;
    today.day = 27;
    today.is_AD = true;
```

A `struct` can even have functions as members! As the above shows, setting data manually is tedious. So, there is a special function that can be added called a *constructor*. Simply name the function the same as the `struct` type name:

```
struct Date {
    int year;
    int month;
    int day;
    bool is_AD;

    Date(int y, int m, int d, bool ad)
    {
        year  = y;
        month = m;
        day   = d;
        is_AD = ad;
    };
};

Date today{2016, 1, 27, true};
```

> What could you do to improve the above constructor? (hint: what's wrong with accepting any input?)

Chapter 9 of the book covers this topic, for more detailed information.

## Computational geometry review
1. Point2D (x,y)
2. LineSegment2D ((x1,y1),(x2,y2))
3. LineSegment2D addition
4. LineSegment2D subtraction
5. LineSegment2D intersection

## Code up a program to do this!

1. Implement Points as structs, then LineSegment2D as structs that have members of the Point2D type.
2. Implement LineSegment2D as structs, then functions for addition and subtraction, returning a new LineSegment2D for the resultant.
3. Implement a LineSegment2D intersection detector.
