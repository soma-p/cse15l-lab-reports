# Lab Report 5 - Putting it All Together
Pranav Kumar Soma

---

## Part 1 - Debugging Scenario

### Original Post:
Hello!

I'm creating a method called ```fibonacci (int n)``` that returns the nth Fibonacci number. I also created two test methods to help test it out, one which covers the base cases of n = 0 and n = 1,
at this point, the numbers 0 and 1 need to be returned, respectively; the other covers non-base cases, specifically n = 5 and n = 6.

However, when I run the tests using the ```test.sh``` script from class, modifying it to include the name of my tester class, I get a very weird output value that says both my tests failed. Here's
the output for reference:

*insert image here*

Furthermore, here's my ```Fibonacci.java``` final:

*insert image here*

### TA Response:
Hi!

I'd suggest you run the program using JDB, I'd say, using the following command: ```jdb -classpath  .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore <nameOfYourTestFile>```.
Maybe try a stop somewhere within your ```fibonacci (int n)```, and see how your test cases run. Hope that helps! :)

### Follow-Up Post:
Hey!

Thank you for your suggestions; I think I figured it out. When I run my code on the debugger, the following process happens: I have no code that checks for 0 as a base case. This leads to me having
an infinite loop, which is why I got that error message so many times! Maybe, along with checking for 0, I should check for numbers less than 0 as well, just to curate all my possible cases.

Here's a picture of what JDB showed me:

*insert image here*


### Setup:

Directory structure needed:
```
- Math
  - Fibonacci.java
  - FibonacciTests.java
  - test.sh
```

```Fibonacci.java``` contains:
```
public class Fibonacci {
    public static int fibonacci(int n) {
        if (n == 1)
            return 1;

        return fibonacci(n - 1) + fibonacci(n - 2);
    }
}
```

```FibonacciTests.java``` contains:
```
import java.util.ArrayList;
import static org.junit.Assert.*;

public class FibonacciTests {
    @Test
    public void testBaseCases() {
        assertEquals(0, Fibonacci.fibonacci(0));
        assertEquals(1, Fibonacci.fibonacci(1));
    }

    @Test
    public void testRecursiveCases() {
        assertEquals(5, Fibonacci.fibonacci(5));
        assertEquals(8, Fibonacci.fibonacci(6));
    }
}
```

```test.sh``` contains:
```
javac -g -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java
java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore FibonacciTests
```

Full Command Line to Trigger the Bug:

```
bash test.sh
```

What to Do to Fix the Bug:
To fix the bug, add a line to the ```fibonacci(int n)``` in ```Fibonacci.java``` that says:
```
if(n == 0) return 0;
```

The resulting file should look like:
```
public class Fibonacci {
    public static int fibonacci(int n) {
        if (n == 0)
            return 0;
        if (n == 1)
            return 1;

        return fibonacci(n - 1) + fibonacci(n - 2);
    }
}
```
---

## Part 2 - Reflection

Something that I am really happy about learning in the second half of this quarter is Vim. Vim, as an editor, becomes really important for me in the future, especially in CSE 30, and
I'm really glad to have the opportunity of reinforced learning with using the text editor. What I really like about Vim is the fact that it makes me super conscious about the decisions I'm making,
especially with the different modes like insert, view, etc, and I really appreciate the tutors and TAs being there for me when I was learning about the true robustness and extensive command abilities of
this text editor. I'm really glad to have learned Vim in an introductory setting before having to use it extensively in CSE 30.
