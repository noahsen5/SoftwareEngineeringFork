# Iteration - looping

Now we have looked at arrays lets explore how to move through the array in c controlled manner. There are many other uses for iteration (or looping).

## While loop

| Task | Details |
| :--- | :--- |
| 1 | As in previous labs, create a new project called "Looping" or similar, delete the comments and replace the code within the function main() with the following: |

```C++
int i = 0;

printf("Start while loop\n");

while (i < 5)
{
    printf("i = %d\n", i);
    i++;        // same as i = i + 1 but more concise;
}

```

| Task | Details |
| :--- | :--- |
| 2    |  In the code above the 'condition' that controls wether the code within the block (inside the {} brackets) is (i < 5). The variable i is assigned the value of 0 before the loop and will be incremented by 1 each time the code in the block is run. How many times do you think the loop will run? Run the program and observe the results. Try changing the value of i before the loop and change the 'less than' operator to 'less than or equals' (<=), what difference does this make? In all there are 6 comparison operators you can try.|

Here is a list:
| Operator | Name  |
| :--- | :--- |
| ==   |Equal to |
| !=   | Not equal         |
| >    | Greater than          |
| <    | Less than         |
| >=   | Greater than or equal to |
| <=   | Less than or equal to         |

## Do - while loop

| Task | Details |
| :--- | :--- |
|   3 |  Change the code within main() to the following:  

```C++
int i = 0;

printf("Start while loop\n");

do
{
    printf("i = %d\n", i);
    i++;        // same as i = i + 1 but more concise;
} while (i < 5);
```

| Task | Details |
| :--- | :--- |
| 4    | The loop shown in the code above is called a 'do - while loop', as you can see it differs from the 'while loop' in that the test condition is at the end (note the semi-colon after the test). Also note that it always runs at least once. Run the program and observe the results, now change the initial value of the variable 'i' to 6 and see what happens. Which loop you choose to use depends on what you are trying to achieve, they both have their uses.

## For loop

The final looping construct is the 'For loop' especially useful when you know how many times you want to loop through a block of code.

The 'for loop' takes this form:

```C++
for (statement1; statement2; statement3)
{

}
```

| Statement | Action  |
| :--- | :--- |
| statement1 | Executed (once) before the execution of the code block |
| statement2 | Is the condition that must be true for the code block to execute |
| statement3 | Executes every time *after* the code block is executed |

| Task | Details |
| :--- | :--- |
|  5 |  Change the code within main() to the following:

```C++
printf("Start the for loop\n");

for (int i = 0; i < 5; i++)
{
    printf("i = %d\n", i);
}

printf("All done looping\n");
```

| Task | Details |
| :--- | :--- |
|  6 |  Run the program and observe the output hopefully it will be the same as for the original while loop. That is because the conditions are the same. The variable i is set to 0 at the start, the condition for looping is that i is less than 5 and every time through the loop i is incremented by 1. The advantage of the for loop is that all the details of how the loop is setup and controlled are in the same place and easy to understand. Again try changing the way the loop runs as you did for the while loop. The for loop is a very common construct and it is important that you understand how it works.

| Task | Details |
| :--- | :--- |
|  7 | Now lets revisit the arrays from a previous lab and use the for loop to look at the individual elements. Change the code within main() to the following:

```C++
char name[6] = "Monty";                                     // an arrays of 5 chars that becomes a string
int nums[10] = { 0, 11, 22, 33, 44, 55, 66, 77, 88, 99 };   // an array of 10 integers

// The sizeof() function returns the number of bytes taken up by the array, to calculate the 
// number of elements divide by the sizeof one element.
printf("The number of elements in name and nums are %zd and %zd\n", sizeof(name)/sizeof(name[0]), sizeof(nums) / sizeof(nums[0]));

printf("The letters in the string are\n");  // Remember it's a string so 5 chars plus the null
for (int i = 0; i <= 4; i++)                // The positions of the chars is 0 to 4 (5 in total)
{
    printf("%c - ", name[i]);       //select each character in turn from the array name[]
    if (i == 4)                     // after the last one print a new line
    {
        printf("\n");
    }
}

int sum = 0;                        // summation of all the array elements
float average = 0.0;                // Average of all the array elements

printf("The numbers in the array are\n");
for (int i = 0; i <= 9; i++)        // There are 10 values in the array in positions 0 to 9
{
    printf("%d - ", nums[i]);       //select each value in turn from the array nums[]
    sum += nums[i];                 // same as sum = sum + nums[i] but more concise    
    if (i == 9)                     // after the last one print a new line or two
    {
        printf("\nSum = %d Average = %f\n", sum, sum/10.0);     // calculate the average and print
    }
}

```

| Task | Details |
| :--- | :--- |
|  8 | There is a bit more going on in this example but this time we have added comments in the code to explain help understanding. Comments are a good way to explain to others what the code does and equally when you come back to your code at a later date they will help you as well. Run the code and observe the results. The important lesson here is the way each element of the array is accessed using it's place. For example the first letter in the array name[] is accessed by the construct name[0]. We use a short 'if'  statement to determine when the for loops get to the end.

## Nested loops

It is possible to put loop inside another - this is known as nested loops.

| Task | Details |
| :--- | :--- |
|  9 | Here is a simple example of nested loops. Change the code within main() to the following:

```C++
// Outer loop 
for (int i = 1; i <= 2; i++)        // Outer loop executes twice
{
    printf("Outer loop number %d\n", i);

    // Inner loop
    for (int j = 1; j <= 5; j++)    // Inner loop executes 5 times for each outer loop run so 10 time in total
    {
        printf("\tInner loop number %d\n", j);  // note the use of the tab (\t) option at the start to improve the layout
    }
}
```

| Task | Details |
| :--- | :--- |
|  10 | Run the code and observe the results, try changing the vaulues for the loop variable. Note we have set the initial values of i and j to 1, you can set them to whatever suits your application. Note also the use of the tab (\t) construct in the printf() function. This is the same as pressing the tab key.
|  11 | This task is to use nested loops to output the classic 'times table'
from early school days, the output should look like this:


![times table](image.png)


## Break and Continue

Sometimes there is a need for finer control over how loops execute, for this we have the statements 'break' and 'continue'. They can be used in 'for loops' and 'while loops'.

| Task | Details |
| :--- | :--- |
|  11 | Replace the code within main() with the following:

```C++
int stopHere = 5;               // this variable could be set by another part of your application

for (int i = 1; i <= 10; i++)   // potentially loop from 1 to 10  
{
    if (i == stopHere)          // check loop counter (i) against the stop variable
    {
        printf("\tLoop stopped at %d\n", stopHere);
        break;                  // break out of the for loop
    }
    printf("Loop counter = %d\n", i);
    // printf("Loop ended loop counter = %d\n", i);
}
// program execution from here when loop exits
```
| Task | Details |
| :--- | :--- |
|  12 | Run the program and observe the results, try changing the value of the variable stopHere. The last line of the code is commented out because it causes a compiler error - why? The task now is to be able to tell wether the loop exited because it had finished it's 10 loops or because it hit the break statement. See if you can amend the program such that the printf() statement at the end can tell how the loop exited. Hint - you need access to the loop variable after it has finished counting - variable scope?

| Task | Details |
| :--- | :--- |
|  13 | The 'continue' statement allows us to control the loop execution in another way. Replace the code within main() with the following:

```C==
int missThis = 5;                                   // these variables could be set by another part of your application
int andMissThis = 7;

for (int i = 1; i <= 10; i++)                       // loop from 1 to 10  
{
    if (i == missThis || i == andMissThis)          // check loop counter (i) against the continue variables
    {                                               // using the 'or' (||) operator. 
    
        printf("\tLoop continue statement\n");
        continue;                                   // continue to the next iteration 
    }
    printf("Loop counter = %d\n", i);
}
// program execution from here when loop exits
```
| Task | Details |
| :--- | :--- |
|  14 | Run the program and observe the results, note that for the loop counter values 5 and 7 the printf() doesn't execute because the continue statement causes the loop to skip straight to the next iteration. The loop still does all 10 loops. Try changing the values of the two variables. Note the use of the 'logical or' operator in the if() statement.


