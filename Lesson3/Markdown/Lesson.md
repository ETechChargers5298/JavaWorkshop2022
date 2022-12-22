# Control Flow Part Two
Now we are able to...
- Take input and print output from users
- Work with variables and values of various data types
- Do various types of operations
- Write comments
- Work with conditional statements
- Work with loops

Our goal this lesson is to expand on our control flows by introducing how we can write we can reuse and write another type of loop that is used commonly. Those are the last control flows left to introduce. We will end the lesson by working with other libaries. So far we have worked with the Scanner library, a library that we used to take in input. There are many other useful libraries to note.

### For Loops
Loops are used to repeat code and we have worked with while loops that repeat code based on a if a condition is met or not. There is another type of loop called the for loop where we can set how many times we want it to loop.

Typically we will write...
```
for(int i = 0; i < [NUMBER OF TIMES YOU WANT TO RUN]; i++) {
    CODE GOES IN HERE
}
```

Lets see an example of this. What if I want to print hello world 10 times.
```java
// This prints hello world 10 times
for(int i = 0; i < 10; i++) {
    System.out.println("Hello World");
}
```

Whats also a nice feature of for loops is it creates a variable i which keeps track of what loop we are on. So on the first loop, i will be 0, second loop it will be 1, third loop it will be 2 and so on.

```java
for(int i = 0; i < 10; i++) {
    System.out.println(i);
}
```

The output is...
```
0
1
2
3
4
5
6
7
8
9
```

### Methods
Methods are the last type of control flow and by far the most used control flow in the way we program in the robotics team. It lets us write code inside a "method" and we can use the method repeadly over and over again.

```
The syntax is...
public void [name of method]() {
    CODE
}

To use a method you do...
[name of method]();
```

What does this all mean, well lets see in the code example below. You can do this better with afor loop in this case but this examples show how methods are used.

```java
// You have to write this at the top of your file to get input
public class Main {
    public static void main(String[] args) {
        // Call the method here
        // Each time you call the method, it means you
        // are running all the code inside the method
        // So this prints Hello World 9 times in total
        printHelloThree();
        printHelloThree();
        printHelloThree();
    }

    // Creates a method to print hello world three times
    // Notice how we make it outside the main method
    public void printHelloThree() {
        System.out.println("Hello World");
        System.out.println("Hello World");
        System.out.println("Hello World");
    }
}
```

#### Parameters

Now how can we make this more useful? We can add parameters. Every method is like a mini program that can also take input and output. The only thing is we need to be very specific about what the inputs or outputs are.

You need to create a variable inside the paratheses of a method for each input you want to take and you have to specify the data type.

```
The syntax is...
public void [nameOfMethod](<data type> <var name>, ...) {

}

The method call is...
[nameOfMethod](value1, ...);
```

Lets see this in action. Lets create a method that adds two numbers up and another that subtracts two numbers up and prints the results. Bonus: A method that checks if a number is negative.

```java
public class Main {
    public static void main(String[] args) {
        // Call the method here
        // Each time you call the method, it means you
        // are running all the code inside the method
        // So this prints Hello World 9 times in total
        addNumbers(1, 2);
        subtractNumbers(1, 2);
        isNegative(1);
    }

    // Method adds two numbers up
    public void addNumbers(double num1, double num2) {
        System.out.println(num1 + num2);
    }

    // Method that subtracts two numbers up
    public void subtractNumbers(double num1, double num2) {
        System.out.println(num1 - num2);
    }

    // Prints if a number is negative
    public void isNegative(double num1) {
        if(num1 < 0) {
            System.out.println("Number is Negative");
        } else {
            System.out.println("Number is Positive");
        }
    }
}
```

#### Returns

So far the only output we have focused on has been printing things out. However, what if lets say we wanted to use the result of a method like `addNumbers` somewhere else in our code instead of printing it. We can using a return statement.

```
So far the syntax has been...
public void [nameOfMethod](<data type> <var name>, ...) {

}

where the void is the return type. If we write `void` it means we are returning nothing. You can also write the data type of what you want to return.

The syntax is now...
public <data type> [nameOfMethod](<data type> <var name>, ...) {

}
```

Lets see this in action. Lets create a method that adds two numbers up and lets use the result again later in the code.

```java
public class Main {
    public static void main(String[] args) {
        // We are storing the result of the method in a variable
        double result = addNumbers(1, 2);
        System.out.println(result);
    }

    // Method adds two numbers up
    public double addNumbers(double num1, double num2) {
        return num1 + num2;
    }
}
```

### Other Libraries
There are many other libraries that we can use to make our code easier to write. We have already used the Scanner library to take in input. There are many other libraries that we can use to make our code easier to write. Here are some of the most common ones. You get a library by writing `import <library name>` at the top of your file.

```java
// We have used this library before
import java.util.Scanner;

// Some other useful libraries
import java.util.Random; // Lets us generate random numbers
import java.lang.Math; // Lets us use math functions like sin, cos, tan, sqrt, etc.
```

#### Random Numbers
The random library lets us generate random numbers. We can use this to generate random numbers for our robot to move.

```java
Random rand = new Random();

int randomNum = rand.nextInt(100); // Generates a random number between 0 and 100
```

#### Math
The math library lets us use math functions like sin, cos, tan, sqrt, etc.

```java
Math.sin(0); // Returns the sin of 0
Math.cos(0); // Returns the cos of 0
Math.tan(0); // Returns the tan of 0
Math.sqrt(0); // Returns the sqrt of 0
Math.pow(2, 3); // Returns 2^3
Math.abs(-1); // Returns the absolute value of -1
Math.max(1, 2); // Returns the max of 1 and 2
Math.min(1, 2); // Returns the min of 1 and 2
Math.round(1.5); // Returns 2
Math.ceil(1.5); // Returns 2
Math.floor(1.5); // Returns 1
Math.log(1); // Returns the natural log of 1
Math.log10(1); // Returns the log base 10 of 1
Math.exp(1); // Returns e^1
Math.toDegrees(1); // Converts 1 radian to degrees
Math.toRadians(1); // Converts 1 degree to radians


// You can also use constants like PI and E
Math.PI; // Returns 3.141592653589793
Math.E; // Returns 2.718281828459045
```

