#Introduction to Programming 10.11.14 - 14.11.14

##Arrays - Basic Info

So far we've worked with different types of data. We've seen integer variables, and chars, and floats, and doubles, and booleans and so on. But the data we've worked with was very small. We were performing operations with just one number or just one char or the name of just one of our friends. But often in programming we have to work with large amounts of data. We have to store the names of not just one friend but hundreds or thousands of users, and then we have to have a way of accessing that information. It'd be extremely tiresome, not to mention masochistic and plain *dumb*, to store all this information in a hundred or a thousand variables. First, we'll have to create those variables. Every single one we'll have to have a name. And we'll have to know beforehand just how many of those we'll need. And the biggest pain of all will come when we have to access this information, because we'll have to know exactly which variable is the one storing it.

### Introduction 
There're many structures programmers have come up with that help them store and access data. The most basic of these structures is the **array**. An array stores a sequence of values that are all of the same type (int, char, bool, etc.). You can imagine it as a variable with a single name that can store multiple values, with each value indexed by a number. The indexes start at 0 so the first element in the array is at index 0, the second is at index 1, and so on.

### Declaration 
A typical declaration for an array in C++ is: `type name [elements];` where type is a valid type (such as int, float, etc.), name is a valid variable name and the elements field (which is always enclosed in square brackets []), specifies the length of the array in terms of the number of elements. **Note** that you can use a variable to create the array, but that variable must be a *constant*. A constant is a variavble whose value, once initialized, cannot be changed. In C++ you can create a constant simply by adding the special word *const* in front of the variable type like this: `const int SIZE = 100;`

You can create different types of arrays:
```
  string names[10];
  char letters[10];
  short smallNumbers[10];
  bool thruths[10];
```

### Size
There are two very important things you must know about arrays. First, **their size is fixed**. You set an array's size when you create it. For example, here's how you can create an array of size 10:  `int numbers[10]`. You can store 10 integers in it, but no more. You can't add an eleventh element to an array of size 10. To do that, you will have to create an array of bigger size, copy all the values from the old array into the new one and then add the eleventh value. As you can imagine, arrays are not very useful when you want to store an unknown number of variables.

### Accessing elements 
The second thing you must know about arrays is that **you can access their elements in constant time**, always. That means there's no difference in performance between accessing the first element of an array, or the 100th element. You can access and change values in an array extremely quickly. For example, here's how you can create an array that stores the numbers from 1 to 100:
```
  const int SIZE = 100;
	int numbers[SIZE];
	for (int i = 0; i < SIZE; i++) {
		numbers[i] = i + 1;
	}
```

As you can see, you can access each element of an array by just typing the array's name and then [] with the index of the element you want to access inside the brackets. `numbers[0] = 1` sets the first element of the array to 1. `numbers[1] = 200` sets the second element to 200, and so on.

##Problems

Enough theory. If you have any questions, you can read about arrays [here (en)](http://www.tutorialspoint.com/cplusplus/cpp_arrays.htm), [here (en)](http://www.cplusplus.com/doc/tutorial/arrays/) and [here (bg)](http://programming-bg.com/%D1%83%D1%80%D0%BE%D1%86%D0%B8/C++/%D0%BC%D0%B0%D1%81%D0%B8%D0%B2%D0%B8). Let's start with the problems.

### 1. You Have Too Many Classmates

Let's begin with a program that shows us exactly *why* we need arrays. To do this, we'll go back to your high school years and the classmates you had then. Write a program that asks you for the names of your classmates, sorted by their class number from 1 to 20+ and then prints the full list to the screen. Write this program first *without* the help of arrays (by creating 20+ different variables... yes, we're bad people) and then **with** an array of strings. 

*Strings are just objects that represent a sequence of characters. For example, `string name = "Baba Qga"` and `string yourFavoriteString = "Hello World"` are both strings.

*The way you would create an array of string is no different than the way you would create an array of ints. For example, to create an empty array of strings of size 24, just write `string classmates[24]`

*To get a whole string (including spaces), use the function [__getline__](http://www.cplusplus.com/reference/string/string/getline/). For example, `getline(cin, yourFavoriteString);` will take the user's input and store it into the variable yourFavoriteString.

### 2. Oldest and Youngest

Write a program that finds the oldest and the youngest among your friends. First, it asks your how many friends you have. You enter the number. Then it asks you to enter exactly that many positive numbers (the ages of your friends). After that, the program shows you who is the youngest and the oldest. [Optionally, you can initialize the array with the ages of your friends like this  `int ages [] = { 42, 10, 11, 33, 19, 18 };`] To find the largest and the smallest number, you can use some of the loops we saw last week.
```
> How many friends do you have?
3
> Enter the ages of your 3 friends:
42
10
19
> The oldest of your friends is 42 years old. The youngest is 10.
```

### 3. What's Your GPA?

Write a program that takes as input 5 of your grades and displays the grade point average. For example:
```
> Enter your grades
6
4
5
5
6
> Your GPA is 5.2
```

### 3. Am I Sorted?

Write a program that tells you if an array is sorted or not. An array is sorted if all of its elements are in descreasing or increasing order. `int array[] = { 1, 3, 45, 566, 4532 }` is sorted. `int array[] = {  4532, 232, 43, 3 }` is sorted. `int array[] = {  4532, 232, 43, 3, 2242 }` is not.

### 4. Insertion Sort

Implement the insertion sort algorithm for sorting. Insertion sort is a simple sorting algorithm: a comparison sort in which the sorted array is built one entry at a time. ![](http://upload.wikimedia.org/wikipedia/commons/0/0f/Insertion-sort-example-300px.gif)

```
function insertionSort(array A)
    for i from 1 to length[A]-1 do
        value := A[i] 
        j := i-1
        while j >= 0 and A[j] > value do
            A[j+1] := A[j]
            j := j-1
        done
        A[j+1] = value
    done
```

### 5. Yarra na esrever!

Write a program that reverses any word you give it. Of course, we'll be using arrays, so the word will have to have a fixed size - let's say 5 or 6 or 7. Store the word into an array of chars.
```
> Enter a word:
reverse
> esrever
```