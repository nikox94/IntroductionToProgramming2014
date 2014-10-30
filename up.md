#Introduction to Programming 27.10.14 - 31.10.14

##Basic Info

The first program most programmers write when they start learning a new language is called *Hello World*. It just prints "Hello World" to your screen. It's popular because, first, it's a visible proof that you can make the computer do whatever you want it to and second, it shows you the basic syntax of the language you're currently trying to learn. Let's see a simple "Hello World" program in C++:
```
#include <iostream>

using namespace std;

int main()
{
  cout << "Hello World!";
  return 0;
}
```
The first line `#include <iostream>`  tells the compiler to take everything in the header file *iostream* and paste it into your program. The header file *iostream* contains basic information about an external library (also called *iostream*) that enables you to handle input from the keyboard and output to the screen. Most of the programs you write will begin with include statements.

We're `using namespace std`. A namespace contains identifiers that help us differentiate between two entities with the same name. `cout` belongs to the std namespace. We're using the cout object to display text to the console. That's actually why we included the `iostream` header *and* introduced the std namespace.

`int main()` is the main function of your program. It returns an integer (which in C++ is of type *int*) - 0. You can miss the return statement - in C++ if your `int main()` function ends without returning anything, 0 is returned by default. `return` statements signal that the particular function has finished execution. 

The line `cout << "Hello World!";` just prints "Hello World" to the console.

## Problems

Now let's write some code. To solve these problems, you'll need to be familiar with the primitive data types in C++. If you have any questions, please refer to [http://www.cplusplus.com/doc/tutorial/variables/] or just ask us.

### 1. Hi, FMI!

As a warm up, write a program that prints "Hi, FMI" to the console.

### 2. Introduce Thyself

Create an integer variable `age` ( for example, `int age = 59` ) and use it to print your age to the console. Output of your program could be:
```
I'm Bill Gates and I'm 59 years old.
```

### 3. Lie Detector

Create `bool` variables `lovePrograming`, `loveLudogorets` and `programShouldHaveNoComments` and set them equal to `true` or `false`. Then print their value to the console.

### 4. Comment Out

Write a program that prints out the names of five of your friends, each on a new line. Once the program compiles and runs, try commenting out different pieces of your code. When does the compiler start complaining? To comment out a line or a part of a line just add `//` in front of the part you want to comment out. The compiler ignores comments - they're only for other programmers. Specifically, try commenting out one of the brackets  - { or }. What happens?

```
#include <iostream>

int main()
{
	//This is a comment
	std::cout << "This is code";
	/*
	This is a comment too.

	It's on multiple lines.
	*/
}
```

### 5. Be A Bootlicker

It's not very fun to write programs that only display hard-coded information. Let's communicate with the user!

In C++ you can take user input using `cin` like this:

```
#include <iostream> 
	
using namespace std; 

int main() 
{ 
	int favoriteNumber; 
 
	cout << "What is your favorite number?" << endl; 
	cin >> favoriteNumber;
	cout << "Oh, " << favoriteNumber << " is my favorite number, too!" << endl; 
	return 0; 
}
```
The line `cin >> favoriteNumber` takes input from the keyboard and stores it into the variable `favoriteNumber`.

Write a similar Bootlicker program that asks the user for their favorite letter / month / etc. and displays it back, saying that's its favorite thing too!

### 6. Grade School Hero

Now that you know how to take user input and store it into a variable, you can write programs that can be useful to other people. Grade schoolers, for example, would be very happy if you gave them a program that can solve their geometry homework!

Write a program that finds the perimeter of a rectangle. The user enters its width and its height and sees the perimeter as the result.
```
Example Input:
3
5
Output:
16
```

### 7. VAT ? I'm Paying HOW Much?

Occasionally, we have to deal with taxes. More than occesionally, actually. In Bulgaria, we have to pay a value-added tax which is a tax on the price of every purchase we make. Let's find out how much we pay in taxes every time we pay for something.

Write a program that asks the user to enter the price of the item we want to buy and the number of items we want to buy. The program then displays how much exactly is our tax. In Bulgaria, the value-added tax is 20% of the price of the product.

Example input & output:
```
Enter the price of the thing you're buying
100
How many items are you going to buy?
3

You're paying 60 lv in taxes.
```

Rewrite the program using floating point numbers.

### 8. How Far Is A From B?

Write a program that asks the user to type the coordinate of 2 points, A and B (in a plane), and then displays the distance between A and B. Use the Distance Formula to calculate the distance.

```
Enter the coordinates of point A
–2 –3
Enter the coordinates of point B
–4 4

Distance is 7.28
```
To solve this problem you can `#include <math.h>`. That way you will be able to use functions in the math library such as sqrt() (which returns the square root of the number you pass as an argument) and pow() which raises a number to a power. For example, sqrt(4) returns 2 and pow(3, 2) returns 9.

### 9.* Will I Be Dead?

Create three integer variables `myAge`, `currentYear` and `compareYear` and let the user enter their values (assume that the user will only enter valid input). The program should tell the user how old they will be in `compareYear`. If `compareYear` is too far in the future (150 years, for example), tell the user the hard truth: they will be dead by then.
