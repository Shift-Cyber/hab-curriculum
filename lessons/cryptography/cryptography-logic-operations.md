# [Cryptography] Logic Operations
*Find out what the 0's and 1's are really about.*

![banner alt text](.rsrc/banner.png)

# Objectives
- Student can identify that 0 represents false and 1 represents true. 
- Student understands how to apply logic operations (Not, And, Or, and Xor) to input values.
- Student understands how to read a truth table.

# Introduction
You often see 0's and 1's floating across computer screens in the movies, but what do these 0's and 1's really mean? 0's and 1's are easy for computers to understand but really hard for humans to understand. In most situations, programming is done using languages like C++, Python, or Java, which have letters and common words that are easier for humans to understand. However, this still gets translated to 0's and 1's so that a computer can understand. In this lesson, we will learn what 0's and 1's represent, and how to do some basic logic operations on these numbers. 

1. What are 0's and 1's anyway?
2. What is a logic operation? 
3. Logic Gate - Not
4. Logic Gate - And
5. Logic Gate - Or
6. Logic Gate - Xor
7. Logic Operations Examples

# Lesson
## What are 0's and 1's anyway? 
To keep it simple, 0 is a value that represents False, and 1 is a value that represents True.

## What is a logic operation? 
These values of 0's and 1's can be manipulated with logic operations such as Not, And, Or, and Xor. There are many more, but we will focus on these 4 logic operations in this lesson. These logic operations are also called logic gates. You can think of a logic gate as a mystery box that takes in something, processes the input, and then gives you an output. In the following sections, we will talk about the inputs and outputs each of these logic gates. 

## Logic Gate - Not
A **Not** logic gate has 1 input and 1 output. 

### Add formal definition of Not gate? 

A **Not** gate takes the input, and makes it *not* the input. For example, if the input value is True (1), then something that is "not true" is False (0). Likewise, if the input is False (0), then something that is "not false" is True (1). 

Below is a truth table, which shows all of the possible inputs and outputs for a **Not** gate. For this **Not** logic gate, there is only 1 input, so there are two input options: 0 and 1. 

|Input  |Output |
|-------|-------|
|0      |1      |
|1      |0      |

## Logic Gate - And
An **And** logic gate has 2 inputs and 1 output. 

An **And** gate takes two inputs, and calculates the output based on the two inputs. The output value is calculated as True if and only if both inputs are True, and as False otherwise. For example, if both inputs are True (1), the output is True (1). If both inputs are False (0), the output is False (0). If one input is True (1) and one input is False (0), then the output is False (0), because only one input is True, which does not satisfy the condition for the output value to be True. 

Below is a truth table, which shows all of the possible inputs and outputs for an **And** gate. Since this **And** gate has 2 inputs, there are 4 possible combinations of the two inputs. 

|Input 1  |Input 2 |Output |
|---------|--------|-------|
|0        |0       |0      |
|0        |1       |0      |
|1        |0       |0      |
|1        |1       |1      |

## Logic Gate - Or
An **Or** logic gate has 2 inputs and 1 output.

An **Or** gate takes two inputs, and calculates the output based on the two inputs. The output is calculated as True if at least one input is True, and as False otherwise. For example, if both inputs are True (1), the output is True (1) since at least one is True. If one input is True (1) and one input is False (0), the output is True (1) since at least one input is True. If both inputs are False (0), the output is False (0) since no inputs are True. 

Below is a truth table, which shows all of the possible inputs and outputs for an **Or** gate. Since this **Or** gate has 2 inputs, there are 4 possible combinations of the two inputs.

|Input 1  |Input 2 |Output |
|---------|--------|-------|
|0        |0       |0      |
|0        |1       |1      |
|1        |0       |1      |
|1        |1       |1      |

## Logic Gate - Xor
An **Xor** logic gate has 2 inputs and 1 output.

An **Xor** gate takes two inputs, and calculates the output based on the two inputs. The output is calculated as True if exactly one input is True (1) and exactly one input is False (0). For example, if both inputs are True (1), the output is False (0). If one input is True (1), and one input is False (0), the output is True (1). If both inputs are False (0), the output is False (0).

Below is a truth table, which shows all of the possible inputs and outputs for an **Xor** gate. Since this **Xor** gate has 2 inputs, there are 4 possible combinations of the two inputs.

|Input 1  |Input 2 |Output |
|---------|--------|-------|
|0        |0       |0      |
|0        |1       |1      |
|1        |0       |1      |
|1        |1       |0      |

## Logic Operations Examples
All of the previously discussed logic gates have either 1 or 2 inputs, and 1 output. Different methods of notation are used to express the different logic operations, but for this lesson, we will use **NOT**, **AND**, **OR**, **XOR** to avoid confusion. 

### Example 1
If x = 1, what is **NOT** x?

Looking at the **NOT** truth table, it can be seen that if the input is 1, the output is 0. **NOT** x is 0. 

### Example 2
If x = 0 and y = 1, what is x **XOR** y? 

Looking at the **XOR** truth table, it can be seen that if if Input 1 is 0 and Input 2 is 1, the output is 1. If you flip the values for Input 1 and Input 2, you would find that the output is still 1. 

### Example 3
Logic operations can also be combined following the rules of operation. 

If x = 1, and y = 0, what is **NOT** (x **AND** y)?

In this situation, we calculate what is inside the parenthesis first: x **AND** y. Looking at the **AND** truth table, it can be seen that if Input 1 is 1 and Input 2 is 0, the output would be 0. Once again, if you flip the values for Input 1 and Input 2, you would find that the output is still 0. 

Now, our operation simplifies to **NOT** 0. Looking at the **NOT** truth table, it can be seen that if the input is 0, the output is 1. Thus, the final solution of **NOT** (x **AND** y) is 1. 


# The Real World, Prolific Breaches
Logic gates are the fundamental building blocks of boolean algebra, where variables are with True (1) or False (0), compared to algebra where variables are any number. In boolean algebra, the basic operations include **And**, **Or**, and **Not**, whereas the basic operations of algebra include addition, subtraction, multiplication, and division. Boolean algebra is a fundamental concept used to design computers, where signals are either high (1) or low (0). By combining logic created from chaining together multiple logic gates, computer programs can be written to do almost anything. 

## Minecraft Calculator
For example, logic gates can be combined in such a way to make a simple calculator. When you type in 25 x 81 into a calculator, a series of logic gates involving inputs of 0's and 1's can be used to determine the answer. In the Minecraft game, there is a building block called Redstone, which can be used to create a calculator based on a specific combination of logic gates. The following video shows the Redstone structure used to build the calculator, and also shows a demonstration of how it is used. 

https://www.youtube.com/watch?v=uGug-4xkw6M

# Check YoSelf
## Q1 - If x=True and y=False, what is the value of x **AND** y?
a. 0 <---<br>
b. 1 <br>

## Q2 - If x=True and y=True, what is the value of x **XOR** y?
a. 0 <---<br>
b. 1 <br>

## Q3 - If x=False and y=True, what is the value of (x **AND** y) **OR** (**NOT** x)?
a. 0 <br>
b. 1 <---<br>


# Keep Going, Next Steps
Check out the following curated resources if you'd like to keep learning about this topic to dominate hard challenges.
1. Detailed Videos on Logic Gates with Minecraft  - https://www.youtube.com/watch?v=hHCSSscy4BI&list=PL5LiOvrbVo8ksCgm_HTLfwhHRdnx11Gms
2. Nand2Tetris Course (Chapters 1-3) - https://www.nand2tetris.org/course
3. Boolean Algebra Game - https://booleangame.com/ 