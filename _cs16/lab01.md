---
layout: lab
num: lab01
ready: true
desc: "for loops, if/else, reading from files, more Unix"
submit_cs: https://submit.cs.ucsb.edu/form/project/811/submission
submit_cs_pnum: 811
---

# NOTE: This labs adapted from CS16 to CCS 1A

This lab is borrowed from Diba Mirza's CS16 and adapted for use in CCS CMPTGCS 1A

Please use the page <{{page.submit_cs}}>, or the Unix shell commmand listed at that
link (e.g. `~submit/submit -p nnn file1 file2 ... filen`) to
submit your assignment rather than the command listed in the instructions if different. 


## Goals for this lab

In this lab you will get practice with
* for loops and while loops
* nested loops
* calculating a series using for loops and if-else statements
* working with other data types (doubles)
* functions
* more practice with using git's web interface

You are not expected to finish the entire lab in one sitting. Please don't rush through it and read all instructions carefully. We encourage you to work in pairs for this lab. Please sit with your pair partner on the same terminal. Decide who will be the 'driver' and who will be the 'navigator'. If you don't know what those terms mean, be sure to see the following video on pair programming:

[http://bit.ly/pair-programming-video](http://bit.ly/pair-programming-video)

To complete the lab follow these steps in order:


# Step by Step Instructions

## Step 1: Log on and create a directory for this lab

* Log into the pilot's CoE account on CSIL and open a terminal. 
* Under your cs16 directory, create a new directory named lab01 (refer to lab00 for instructions if you have forgotten how to do this)

You are now ready to get the starter code.

## Step 2: Getting the starter code  <a name="getstarter"></a>

Copy the code from the instructor's account on the CSIL server into your local git directory. If your local git directory is lab01_alily_jgaucho issue the following command:

```
  cp /cs/faculty/dimirza/cs16-sp17/labs/lab01/* ~/cs16/lab01/
```

You may get some permission errors for some files, such as those listed below.  If you do, don't worry about it.

```
-bash-4.3$ cp /cs/faculty/dimirza/cs16-sp17/labs/lab01/* ~/cs16/lab01
cp: cannot open '/cs/faculty/dimirza/cs16-sp17/labs/lab01/a.out' for reading: Permission denied
cp: cannot open '/cs/faculty/dimirza/cs16-sp17/labs/lab01/min3v1' for reading: Permission denied
cp: cannot open '/cs/faculty/dimirza/cs16-sp17/labs/lab01/myexec' for reading: Permission denied
-bash-4.3$ 
```

Even if you get those errors, after doing this command, if you cd into ~/cs16/lab01/ and use the ls command, you should see three .cpp files and a README:

```
-bash-4.2$ ls
min2.cpp  min3v1.cpp  min3v2.cpp README.md
-bash-4.2$ 
```

If you don't see those files, work with your pair partner to go back through the instructions and make sure you didn't miss a step. If you still have trouble, ask your mentor for assistance. 


## Step 3: Solving the problems for this lab<a name="programs"></a>

If you are in a pair, make sure you switch the driver and navigator roles at this point. You must switch roles twice more before the end of the lab.
This assignment consists of 3 problems, each of which is described below. The first one is worth 20 points each, and the last two are worth 40 points each. Each should be solved in its own file and all three must be submitted for full assignment credit. These exercises are inspired by the ones from the textbook (in Ch. 2 and Ch. 3) - but they are NOT the same, so follow the instructions on THIS sheet carefully. 

You will need to create <b>three files named block.cpp, min4.cpp, and pi.cpp</b>:
Each corresponds to one of the problems listed below, which make up this lab.

For a reminder on how to open and use a text editor to create and edit new source files, refer back to Lab #0. 

For all the subproblems given in this assignment you must compile your code frequently (as you develop it), and test it extensively with as many inputs as you can think of. 

<hr>

### Print a block

* Navigate to your lab01 directory using the cd command
* open a file called `block.cpp` using the same editor you used for the previous labs. 
* In that file, write a program that takes an input from a user for the number of rows and number of columns and prints out a block of characters that is based on these 2 parameters. The program should keep asking the user for input, and printing out the result, until the user enters zero for each of the input parameters.

A session should look <b><i>exactly</i></b> like the following example (including whitespace and formatting - note that there is no whitespace at the end of each of these lines), for all the different inputs and the output:

<img src="block.png" width="700" alt="block program example" />

Each string printed by the program should include a newline at the end, but no other trailing whitespace (i.e. extra space characters at the end of the line).

For this problem you have to use a for-loop and a while loop. We covered for-loops in class. While loops are similar in that the code inside the body of the while is repeated as long as the while condition is true. We will talk about this more in the next lecture. Here is the syntax for while

```
while('expression'){
	//Repeat these statements
}
```

'expression' should be replaced by the appropriate boolean expression. The body of the loop is executed as long as the expression is true. e.g.

```
int x=5;
while(x>0){
    cout <<x<<" ";
	x--;
}
```
The above code prints 5 4 3 2 1.


To compile your code use the g++ command as in lab01 OR the simple make command as in lab01

`$ g++ -std=c++11 -o block block.cpp` 

OR

```
make block
```

If you used the first option (g++ ...) note that the -std=c++11 option in these commands is optional to use (that is, not critical to define). All this does is force the compiler to use the latest version of C++.

If you used the second option (make...) note that the make program is clever to compile only block.cpp into the block executable, even though there are other programs (cpp files) in that directory. Note that the C++11 compiler will not be used in the default make tool. But that should be okay for now.


<b>If you encounter an error, use the compiler hints and examine the line in question. If the compiler messsage is not sufficient to identify the error, you can search online to see when the error occurs in general.</b>

Run your executable as follows to test it out.
`$ ./block`

Remember to re-compile the relevant files after you make any changes to the C++ code.


<hr>


### Calculate the approximate value of PI

Switch roles with your partner.

Write a C++ program in ```pi.cpp``` that approximates the value of the constant π. Once again you should not resort to using predefind constants and functions for π, that are provided by C++ standard libraries. Instead you should compute the value of π based on the Leibniz formula for π. The formula is given below:

```
 1 – 1/3 + 1/5 – 1/7 + 1/9 ...  = pi/4
```

Put another way, the formula can be written as:

```
pi = 4 · [ 1 – 1/3 + 1/5 – 1/7 + 1/9 ... + (–1 ^ n)/(2n + 1) ]
```

The Leibniz formula works well for high values of n.

The program takes an input from the user for the value of n, which determines the number of terms in the approximation of the value of pi. The program then outputs the approximated value of pi as calculated by the Leibniz formula. You must also include a loop that allows the user to repeat this calculation for new values of 'n' until the user says she or he wants to end the program by issuing an input of -1 (or any other negative number). You may assume that the user always inputs an integer. 

The program should print a string of text to the terminal before getting each piece of input from the user. A session should look like the following example (including whitespace and formatting), showing the expected output for different inputs:

```
Enter the value of the parameter 'n' in the Leibniz formula (or -1 to quit):
0
The approximate value of pi using 1 term is: 4.000
Enter the value of the parameter 'n' in the Leibniz formula (or -1 to quit):
3
The approximate value of pi using 4 terms is: 2.895
Enter the value of the parameter 'n' in the Leibniz formula (or -1 to quit):
9
The approximate value of pi using 10 terms is: 3.042
Enter the value of the parameter 'n' in the Leibniz formula (or -1 to quit):
49
The approximate value of pi using 50 terms is: 3.122
Enter the value of the parameter 'n' in the Leibniz formula (or -1 to quit):
99
The approximate value of pi using 100 terms is: 3.132
Enter the value of the parameter 'n' in the Leibniz formula (or -1 to quit):
999
The approximate value of pi using 1000 terms is: 3.141
Enter the value of the parameter 'n' in the Leibniz formula (or -1 to quit):
9999
The approximate value of pi using 10000 terms is: 3.141
Enter the value of the parameter 'n' in the Leibniz formula (or -1 to quit):
-1
```
Be sure to have a newline after each "Enter the value..." prompt and no other white spaces.

Here is a link that gives the approximated values of pi for up to 1000 terms: [http://www.eveandersson.com/pi/gregory-leibniz](http://www.eveandersson.com/pi/gregory-leibniz)

In addition, all approximated floating pointer numbers must be displayed to exactly three digits after the decimal point. To do this you should use set the precision for displaying floating point numbers before any of the cout statements in your code. This is done as follows:

```
cout.setf(ios::fixed); 	   // Display in fixed point notation. For example, display 1e-1 as 0.1 
cout.setf(ios::showpoint); // Always display the decimal point.
cout.precision(3);         // Set the number of digits to display after the decimal point to 3
```



<hr>


### Calculate the minimum of 4 numbers

Switch roles with your partner. 

In this part of the lab you will write a program that compares 4 input numbers and prints out the smallest one. 

**You should not use the *min()* function in C++ algorithm library or any other outside function that performs the minimum operation for you. Instead, you should base the program on the example programs provided to you that compare fewer inputs.** 


Start by examining the given examples, also described below:

<b>min2.cpp</b>

This program takes two command line arguments, and converts them to integers.  It then calls a function, smallest_of_two, that returns the smallest of the two numbers (or the value they share in case of a tie.) It then prints out the result of that function call.

<b>min3v1.cpp</b>

This is the first of two versions of a program that takes min2.cpp one step further, finding the smallest value from among three numbers. Again, if there is a tie, it prints the tie value. Look at the nested if/else statements and see if you can make sense of the logic. Seek help if you don't.

<b>min3v2.cpp</b>

This program does EXACTLY the same thing as min3v1.cpp, but does it with much cleaner, simpler code. Notice how we REUSE the smallest_of_two function to build up a smallest_of_three function. 

Your job in this step is to test min2, min3v1 and min3v2 with many different values and convince yourself that they work properly.

In the next step, you will be taking these programs to the next logical step in this sequence.

<b><i>Your main task</i></b>: Write min4.cpp

* Write a program that works just like min2 and min3v1 and min3v2, except it takes four ints on the command line, and prints the smallest value, handling ties appropriately.

* We encourage you to follow the model of min3v2.cpp if you can understand how this works, since your code will be far cleaner than trying to build this out of nested if/else statements.

If you DO use nested if/else statements, though, be sure that you indent and format your code appropriately.

Follow the pattern in min2 and min3v1/min3v2 in terms of all other issues and how they are handled, including the usage message, etc. Your program should look exactly like these except that it works on 4 inputs (note, there are no trailing whitespacse):

<img src="min4.png" width="500" alt="min4 program example" />

To compile your code use the g++ command as before.

`$ g++ -std=c++11 -o min4 min4.cpp`

Run your executable with different inputs to test it out.

<hr>

## Step 5: Submit your code<a name="submit"></a>

Once you are satisfied that your programs are correct, it is time to submit them. If you are working in a pair you should do the following steps to join the same group on submit.cs

### Joining the same group

* Navigate to https://submit.cs.ucsb.edu
* Go to CMPTGCS_1a_f17
* Click on the cs16_lab01 page. You will see a blue button named “Join Groups” on top of the page, Click on the button
* Click on you and your partner’s name. Create group.


### Submitting the assignment
Note: Please remember that you must submit the programs to obtain any credit for the assignment; just completing the programs is not enough.

*Submitting via the web interface*

* In general, to submit via submit.cs, you should login at https://submit.cs.ucsb.edu, then navigate to the page for this course, and the page for this lab number.  
* Or just visit this direct link: <{{page.submit_cs}}>
* Then click “Make Submission”, and make your submission. Remember to submit all of the files that submit.cs is expecting (and with exactly the file names it expects.)
* Once you submit, you should see a page detailing your submission. The system will automatically grade your program and will show you the results on this page after a 1 minute delay.

*Submitting via command line*

You can alternatively submit your code from the command line (terminal) on any CS machine, including the Phelps lab machines or the CSIL server. You can use this method when logged in remotely or while on the csil machines. This is the preferred method of submitting.

Submit all the source files to this assignment by running the command:

<tt>~submit/submit -p {{page.submit_cs_pnum}} block.cpp min4.cpp pi.cpp</tt>

The project number `811` comes from the submit.cs link for this program, i.e. <{{page.submit_cs}}> )

You can copy the URL shown in the output of the above and paste into a web browser to reach the submission result page.

## Check Submission Results<a name="checksubmission"></a>

After the 1 minute delay, the submit system will show your score and give you feedback on your submission. Refresh the webpage after a minute to see this information.

You may submit this lab multiple times. You should submit only after local compilation does not produce any errors and runs as expected. The score of the last submission uploaded before the deadline will be used as your assignment grade.


## Done!<a name="done"></a>

You are now done with this assignment!
If you are in the Phelps lab or in CSIL, make sure to log out of the machine before you leave. Also, make sure to close all open programs before you log out. Some programs will not work next time if they are not closed. Remember to save all your open files before you close your text editor.

If you are logged in remotely, you can log out using the exit command:

`$ exit`


## Grading rubric 
In addition to the points given by submit.cs, our staff will be manually grading your work and giving you points based on the following rubric:
* (1 pt) Submitting on time, per instructions
* (2 pts) Code style, including but not limited to:
1. Code can be easily understood by humans familiar with C++ (including both the author(s) of the code, and non-authors of the code.)
2. Code is neatly indented and formatted, following standard code indentation practices for C++ as illustrated in either the textbook, or example code given in lectures and labs
3. Variable names choices are reasonable
4. Code is reasonably "DRY" (as in "don't repeat yourself")&mdash;where appropriate, common code is factored out into functions
5. Code is not unnecessarily or unreasonably complex when a simpler solution is available

* (1pt) Demonstrate an understanding of the use of for-loops and if-else structure to mentor. Mentor will ask you to explain your block program at check out 
* (1pt) Demonstrate an understanding of pair programming to your mentor. 


</div>

