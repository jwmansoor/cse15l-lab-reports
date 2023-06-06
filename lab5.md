# Lab Report 5: Debugging and Reflection

## Part 1: Edstem Debugging Scenario

---
**1. Student Edstem Post**

**What environment are you using (computer, operating system, web browser, terminal/editor, and so on)?**

My computer is a Macbook Pro 2022 and the operating system is Mac-OS Ventura 13.4. I am using Virtual Studio code.  

**Detail the symptom you're seeing. Be specific; include both what you're seeing and what you expected to see instead. Screenshots are great, copy-pasted terminal output is also great. Avoid saying “it doesn't work”.**

The output should be a message saying `OK. two tests passed`, signaling that our tests compiled, ran, and passed. I don't understand the error message I am getting instead. I was trying to write a test to check for errors in my method, `reversed` in the ArrayExamples class. However, when I compile and run my code, I keep getting this error message.  It says the location is in the ArrayExamples class, but when I look there I see everything is ok and there is no apparent error in my code. I guess it is because of where I placed my method, because the error says it cannot find the symbol. I guess the symbol it is reffering to is my method. Can you help me fix my code, please? 

<img width="1018" alt="Screenshot 2023-06-05 at 10 52 48 PM" src="https://github.com/jwmansoor/cse15l-lab-reports/assets/130420272/7483ded8-1fb8-4172-b156-d42a53cb4310">

<img width="614" alt="Screenshot 2023-06-05 at 11 47 28 PM" src="https://github.com/jwmansoor/cse15l-lab-reports/assets/130420272/f9b6bcb0-43fe-4389-bf7d-3125a5dcf16a">

Furthermore, in my bash script file, I don't understand why the command in my code is not found. I expected to see it run and print `it was not one` without saying that the `command is not found`. I guess it is because of me typing something in wrong in my `if statement`, but I am not sure. 

<img width="1013" alt="Screenshot 2023-06-05 at 11 46 48 PM" src="https://github.com/jwmansoor/cse15l-lab-reports/assets/130420272/27fda8b6-079e-4fbc-ab7b-6bcbb983f605">

**Detail the failure-inducing input and context. That might mean any or all of the command you're running, a test case, command-line arguments, working directory, even the last few commands you ran. Do your best to provide as much context as you can.**

Here is the code for the method that is giving me an error: 
```
   static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - 1];
    }
    return arr;
  }
 ```

Here is my J-Unit test: 

```
@Test 
  public void testReversed() {
    double[] input1 = { }; 
    assertArrayEquals(new int[]{ }, ArrayExamples.testReversed(input1)); 
  } 
```

My working directory is lab3-main, and I am in it as you can see from the screenshot. The commands I ran to compile and run my code are from the course website, lab 3: 

```
$ javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java
$ java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ArrayTests
```


Here is my output: 
```
jenny@Jennys-MacBook-Pro lab3-main % javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java
ArrayTests.java:16: error: cannot find symbol
    assertArrayEquals(new int[]{ }, ArrayExamples.testReversed(input1));
                                                 ^
  symbol:   method testReversed(int[])
  location: class ArrayExamples
1 error
```

**For one.sh**, here is my buggy code: 
```
ONE=3

if [1 -eq $ONE]
then
  echo "it was 1"
else 
  echo "it was not 1"
fi
```
Here is my output: 
```
jenny@Jennys-MacBook-Pro lab3-main % bash one.sh
one.sh: line 3: [[1: command not found
it was not 1
```

--- 
**TA Response**

Hi! I see that the error message you are getting has to do with your J-unit test and not your `reversed` method. I would suggest checking the `assertArrayEquals` part of the JUnit test you wrote for that method. Specifically, look at your arguments for `assertArrayEquals`. Do you see how the error points to the symbol it cannot find, which is actually the method `testReversed` and not `reversed`. It mentions the symbol is `testReversed` and the location it cannot find it in is ArrayExamples class, because `testReversed` is not in the ArrayExamples class. Do you think that `ArrayExamples.testReversed` would be a logical argument if `testReversed` is not found in ArrayExamples class? Consider changing your second argument for `assertArrayEquals`. As for your bash script file, check the spacing and syntax in your code. Consider looking at the examples from class of bash script code and make a minor fix. Think, what should the output be? 

P.S. Another minor bug you have that is not pointed out by your terminal yet is on line 17, in your `for loop`. Are you assigning the right value to arr[i]? What did you forget to subtract from arr.length to get the right output?

--- 

**2. Fixing the Code**


I totally understand where I made the mistake. It is clear that I put in the wrong argument for `assertArrayEquals` in my JUnit test. `testReversed` is not a method inside the ArrayExamples class so calling it like that is wrong. Furthermore, I am even not supposed to be calling `testReversed` because I am coding inside the `testReversed` method and I want to check the `reversed` method. Therefore, to fix my code, I changed the argument to `ArrayExamples.reversed(input1)`. I also fixed the bug in my `for loop` on line 17 of ArrayExamples.java by subtracting `i` as well as `1`. Therefore, I got the output shown here: 

<img width="1017" alt="Screenshot 2023-06-05 at 11 01 53 PM" src="https://github.com/jwmansoor/cse15l-lab-reports/assets/130420272/dbcd4588-4c74-497b-a370-112702f67969">


As for the bash script file, I understand that I had the wrong syntax. I fixed it by looking at my lecture handouts and focused on the spacing. I got the following result like I expected: 

<img width="1016" alt="Screenshot 2023-06-05 at 11 51 04 PM" src="https://github.com/jwmansoor/cse15l-lab-reports/assets/130420272/fafba7de-c759-40d3-a004-df8add3cdf60">


---

**3. Setup Information**

* My code was from the [lab 3](https://github.com/ucsd-cse15l-w23/lab3) directory. The files that had my code + bugs were `ArrayExamples.java` and `ArrayTests.java`. 
* I added the bash script file, `one.sh` 
* The contents of each file before fixing the bug were: 

**ArrayExamples.java**

```
public class ArrayExamples {

  // Changes the input array to be in reversed order
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }

  // Returns a *new* array with all the elements of the input array in reversed
  // order
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - 1];
    }
    return arr;
  }

}

```

**ArrayTests.java**
```
import static org.junit.Assert.*;
import org.junit.*;

public class ArrayTests {
	@Test 
	public void testReverseInPlace() {
    int[] input1 = { 3 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 3 }, input1);
	}

  @Test
  public void testReversed() {
    int[] input1 = { };
    assertArrayEquals(new int[]{ }, ArrayExamples.testReversed(input1));
  }
}
```

**one.sh**
```
ONE=3

if [1 -eq $ONE]
then
  echo "it was 1"
fi
```

* Command-line to trigger bug: 
```
$ javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java
$ bash one.sh
```
* A description of what to edit to fix the bug: 
    * To fix the bug, I changed the second command for `assertArrayEquals` in my JUnit test to `ArrayExamples.reversed(input1)`. 
    * I also changed the body of my for loop in my `reversed` method. I changed `arr[i] = newArray[arr.length - 1];` to `arr[i] = newArray[arr.length - i -1];`. In other words, I added the code `-i` inside the brackets to subtract `i` as well as 1 from `array.length`. This fixes the bug and made my tests pass. 
    * Furthermore, on the bash file, I had to add another pair of brackets to the condition in my `if statement` as well as a space between the inner brackets and the text inside. I changed it to `if [[ 1 -e $ONE ]]`. For bash, it is important to keep the exact spacing. If the syntax isn't right, then the command won't run. 

## Part 2: Reflection
  I remember the first half of the quarter when my tutor first showed me how to log in to connect to a remote web server, `ieng6`, using the `ssh` command. I then learned to create my own webserver by compiling and running the pre-coded files, `Server.java` and `StringServer.java`, and it was so interesting to me that I used to get excited for lab because that meant more guided exploration in those topics. In the second half of the quarter, I was introduced to new things like bash as well as new command-line techniques that I had never explored before. Something specific that stood out to me was learning how to code an autograder in lab. The coding challenge in lab 6 was the lab that I enjoyed most, because my lab partner and I worked on java/bash files and ran Junit tests to put together an autograder like the one in [Gradescope](https://www.gradescope.com/). Learning how to put something like `grade.sh` together by applying lecture concepts as well as challenging ourselves was actually fun. I even enjoyed debugging others' autograders and adding comments in lab #8 because it helped me notice commnon mistakes and what to avoid doing. Moreover, something cool that I learned from my lab partner last week was opening my terminal using a keyboard shortcut. I used to always open my terminal by going on the top bar in my computer and clicking on `Terminal` then clicking on `New Terminal`, but now I just use the keyboard shortcut and type in ` control ` + ``` ` ```. Since I did lab report 3 about the command `grep`, I learned multiple ways of using it in my terminal, some of them being really cool like `grep -n -color`. That command did not only search for a `string` and print its line in the terminal, but it also pointed out its exact location by changing its color to red and displaying the line number on the left side. That modification made the `grep` command more efficient, and I learned about it from researching it in lab report 3. To conclude, these are just a few new things I learned that stood out to me. However, over the course of the last half of the quarter, I developed new knowledge and skills for Java, command-line arguments, Bash, debuggers, etc. 
