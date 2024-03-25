# The Basics

### Comments

Comments are used to tell the C# language that a certain section of your code should not be treated as actual code and
should be ignored they are often used document code and temperately remove sections of code

There are two ways to comment the first way is to put two <code>//</code> in front of the section of code you want to
comment everything that comes after <code>//</code> will be treated as a comment
<code-block lang="c#">
//This is a comment
//Notice how I have to always put these // before each line to keep it commented
This is not a comment //Everything in the line before the // will not be treated as a comment
</code-block>
The second way to comment is to surround the section of code to be commented with <code>/*</code> <code>*/</code> everything that comes between these two symbols will be treated as a comment
<code-block lang="c#">
/*This is also a comment*/
/* Notice how
I don't have to keep
putting anything at the begging of each new
line to keep the code commented */
</code-block>
<code>//</code> is better for commenting single or a few lines while <code>/* */</code> is better for commenting big sections

### Data Types

| Data Type | Description                                                                                          |
|-----------|------------------------------------------------------------------------------------------------------|
| bool      | Can store one of two values true or false                                                            |
| int       | Stores whole numbers (integers) ranging from -2.1 billion to +2.1 billion                            |
| long      | Similar to int also stores whole numbers (integers) but can store larger number then int             |
| float     | Stores numbers including decimal values                                                              |
| double    | Similar to float also stores decimal values but with increased precision and can store larger values |
| decimal   | Similar to float and double stores decimal values with perfect precision                             |
| char      | Stores one character                                                                                 |
| string    | Similar to char but stores more then one character                                                   |

### Initialising and declaring variables

In these examples we are only declaring a variable
<code-block lang="c#">
string personName;
</code-block>

<code-block lang="c#">
int numberOfMarbles;
</code-block>

In these examples we are initializing a variable
<code-block lang="c#">
personName = "Nolan";
</code-block>

<code-block lang="c#">
numberOfMarbles = 27;
</code-block>

To save us some writing we can do both at operations at the same time
<code-block lang="c#">
string personName = "Nolan";
</code-block>

<code-block lang="c#">
int numberOfMarbles = 27;
</code-block>

### Concatenation and Operators and Console.WriteLine()

<code>+</code> This is the concatenation operator when acting on string it will put the string together without spaces in between

<code-block lang="c#">
coolString = "cool" + "Thing";
Console.WriteLine(coolString);
</code-block>
Output:<code>coolThing</code>

<code>+</code> Will also add two or more integers, floats value or similar together

<code-block lang="c#">
int i = 100 + 25;
Console.WriteLine(i);
</code-block>

Output: <code>125</code>

<code>-</code> This is the negative operator it will subtract one integer, float value or similar from anouther
<code-block lang="c#">
int i = 100 - 25;
Console.WriteLine(i);
</code-block>

Output: <code>75</code>

<code>*</code> This is the multiplication operator it will multiply two integer, float value or similar together
<code-block lang="c#">
int i = 5 * 5;
Console.WriteLine(i);
</code-block>

Output: <code>25</code>

<code>/</code> This is the division operator it will divide two integer, float value or similar
<code-block lang="c#">
int i = 25 / 5;
Console.WriteLine(i);
</code-block>

Output: <code>5</code>

Remember that when dividing integers we don't always get a whole number in the last example we were lucky 25 divided by 5 is 5 exactly but take the next example

<code-block lang="c#">
int i = 5 / 4;
Console.WriteLine(i);
</code-block>

Output: <code>1</code>

Our output is zero because integer values can only store whole numbers or integers as such C# will round the actual answer <code>1.25</code> to <code>1</code>

<code>%</code> This is the modulo operator it will find the remainder of division of one integer, float value or similar to anouther

<code-block lang="c#">
int i = 6 / 5;
Console.WriteLine(i);
</code-block>

Output: <code>1</code>

### Loops

### For Loops

The first statement will be executed on the loops first run

The second statement will be checked to see if true everytime the loop runs if statement not true then loop will exit

The third statement will executed everytime the loop completes successfully

Here is an example of a loop that starts at 1 and will count up until it hits 100


```` c#
for (int i = 1; i <= 100; i++)
{
    Console.WriteLine(i);
}
````

### While loops

While loops are much simpler instead of having three statements we only have one which will tell the loop to continue looping as long as the statement continues to be true

In this example we have a loop that will continue on indefinitely
```` c#
int i = 0;
while (true)
{
    i++;
    Console.WriteLine(i);
}
````

### Arrays

In this example we are making an empty integer array where the user input specifies the array length
<code-block lang="c#">
int n = Convert.ToInt32(Console.ReadLine());
int[] coolArray = new int[n];
</code-block>

Remember that C# uses a zero based index this means that the length of the array (the number of slots the array has)
will be equal to n-1

Arrays can also be made and assigned values using the following syntax
<code-block lang="c#">
//For string array
string[] cars = {"Volvo", "BMW", "Ford", "Mazda"};
</code-block>

<code-block lang="c#">
//For integer array or similar
int[] myNum = {10, 20, 30, 40, 50, 60, 70, 80};
</code-block>

With these arrays the size of the array needed will be automatically calculated for you for example the first array will
have a length of 4 second will have a length of 8

### Making Methods

In this example we are making a method that takes in two integers adds them together and writes the result to console
<code-block lang="c#">
static void myMethod(int n, int m)
{
    int j = n + m;
    Console.WriteLine(j);
}
</code-block>
This array can them be used with the following syntax or similar
<code-block lang="c#">
int michelAge = 24;
int joshAge = 19;
myMethod(michelAge, joshAge);
</code-block>
Take note of the fact that the <code>n</code> and <code>m</code> variables are declared and assigned values from or input variables

Please note that variables declared inside an array in our example <code> n </code>, <code> m </code> and <code>
j </code> are not accessible outside the array

In our last example we created a void method void methods are special in the fact that they do not need to return a
value

In this example we are going to modify are method into returning an integer value that we can use inside
of <code lang="c#"> Console.WriteLine() </code> instead of having the method write to <code lang="c#">
Console.WriteLine() </code> directly
<code-block lang="c#">
int michelAge = 24;
int joshAge = 19;
Console.WriteLine(myMethod(michelAge, joshAge));
static int myMethod(int n, int m)
{
    int j = n + m;
    return j;
}
</code-block>