# Lab Report 5

# Part 1 - Debugging Scenario

Student :
Hello, I have been trying to reverse my array in place however some of the junit tests are failing.
```
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
}
```
 When I try to run the following test it fails :
```
@Test 
public void testReverseInPlace2() {
    int[] input1 = { 0, 1, 2, 3 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 3, 2, 1, 0 }, input1);
}
```
This is the output I get :
![Image](err.png)

The screenshot above indicates that the expected output of the reversal of `{ 0, 1, 2, 3 }` was `{ 3, 2, 1, 0 }` but instead the program produced something else.

I would really appreciate it if you could help me out here.

TA :
Hey there, 
To figure out the exact bug I would suggest running jdb. You could try the following commands to identify the bug :   
* To compile the code : `javac -g -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java`
* To run the debugger : `jdb -classpath .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore [Name of your test file]`
* Create a break point at the line where your test fails
* run jdb : you can use the `run` command
* print the local variables of the array to identify what is going on : `print [variable name]`

Hopefully this helps you identify the bug. 
  

# Part 2 - Reflection

Overall, this course has been incredibly enlightening. Before this, I had never delved so deeply into terminal usage. Yet, after nine weeks of predominantly terminal-based work, I've grown to value its tool. One aspect that stood out to me was the process of constructing an autograder. Exploring the different ways of building anautograder using bash and java has been quite interesting. 



