
# Exp.No:33 POSTFIX EVALUATION
# AIM
To write a Python program to evaluate a user-given Postfix expression that contains Multiplication and Addition operators using the stack concept.

# ALGORITHM
Start the program. Define a set named OPERATORS containing all the valid operators: *, +, **, -, /, %. Define a function evaluate_postfix(exp) to evaluate the postfix expression: Inside the function, create an empty list called stack to store operands and intermediate results. Loop through each item in the given postfix expression: If the current item is not in OPERATORS, it is an operand, so append it to the stack. If the current item is an operator: Pop the top two elements from the stack (first pop is a, second pop is b). Perform the operation b a depending on the current operator. Store the result in a variable called result. Append the result back to the stack. After the loop ends, return the first element of the stack as the final evaluation result. Take a postfix expression as input from the user. Print the postfix expression. Call the function evaluate_postfix() with the input and print the result. End the program.

# PROGRAM
~~~
Reg - 212222060245 Name - Singamala Rakshitha

OPERATORS=set(['*','+']) 


def evaluate_postfix(expression):
    stack=[] 
    for i in expression:
        if i not in OPERATORS:
            stack.append(i)  
        
        else:
            a=stack.pop()  
            b=stack.pop()
        
            if i=='+':
                res=int(b)+int(a)  
            elif i=='*':
                res=int(b)*int(a)
            
            stack.append(res) 
    return stack[0]

expression = input()
print('postfix expression: ',expression)
print('Evaluation result: ',evaluate_postfix(expression))
~~~

# OUTPUT
<img width="1200" height="226" alt="image" src="https://github.com/user-attachments/assets/13cc08bb-b9c6-4186-ac0f-7f489bf7ac21" />

# RESULT
Thus the program to evaluate a user-given Postfix expression has been implemented and executed succesfully.
