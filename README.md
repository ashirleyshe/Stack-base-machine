# Stack-base-machine
### Problem description
Stack-base machine is a kind of cpu design architecture which
sometimes be compared with register-based machine. Unlike
register-based machine which used 3 address code taking 1 opcode
and 2 corresponding operand e.g. add %eax, 3, stack based machine
was designed with opcode with one or zero operand and one long
stack which served as registers to take temporary value in calculation.  

In this problem, you will be given a program for stack-based machine.
You need to write a yacc program to check if the format of the
program and evaluate its result. The instruction set of our machine
are: “add”, “sub”, “mul”, “mod” which will pop 2 operand from stack
then perform addition, substraction, multiplication and modulation
and push back the result, “inc”, “dec” which will pop 1 operand from
stack then perform increased by 1, decreased by 1, then push back
the result, “load <number>” which will push a constant <number> on
the top of the stack.

**Sample Input 1:**  
load 1  
load 2  
sub  
load 5  
mod    
**Sample Output 1:**  
0  
**Explanation 1:**  
5 % (2-1) = 0  


**Sample Input 2:**  
load 3  
load 4  
inc  
inc  
**Sample Output 2:**  
Invalid format  
**Explanation 2:**  
If after finish the program, there 
are more than 1 numbers in the
stack it will be consider invalid.  

**Sample Input 3:**  
load 1  
load 1  
add  
sub  
**Sample Output 3:**  
Invalid format  
**Explanation 3:**  
No enough operands in stack to perform sub.  

**Sample Input 4:**  
load 1  
inc  
inc  
dec  
load 3  
inc  
inc  
mul  
load 4  
dec  
dec  
mul  
inc  
**Sample Output 4:**  
21
