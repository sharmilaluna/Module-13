# Exp.No:32 CONVERSION OF INFIX TO POSTFIX
# AIM
To write a Python program to convert a given Infix expression to Postfix expression by following the precedence and associative rules. The input expression contains only Division, Subtraction, and Bitwise AND operators. A dictionary is used to set the priority for operators, and a set is used to hold the operators used in the given expression.

# ALGORITHM
Start the program. Initialize an empty stack and an empty output string. Iterate through each character in the infix expression: If the character is not an operator, append it directly to the output string. If the character is an open parenthesis '(', push it onto the stack. If the character is a close parenthesis ')', pop from the stack and append to the output until encountering a left parenthesis '('. If the character is an operator, handle it based on precedence: While there’s an operator at the top of the stack with higher or equal precedence, pop the stack and append those operators to the output. Push the current operator onto the stack. Use a priority dictionary to define operator precedence, ensuring higher precedence operators are placed before lower precedence ones. Once the expression is fully processed, continue popping any remaining operators from the stack and append them to the output. Return the final postfix expression. Print the result. End the program.

# PROGRAM
~~~
Reg - 212222090019 Name - D.Preethika 

OPERATORS = set(['&','-','/','(',')'])
PRIORITY = {'&':1,'-':2,'/':3}

def infixToPostfix(expression):
    stack = []
    output = ''

    for character in expression:
        if character not in OPERATORS:            # if operand (A, B, etc.)
            output += character
        elif character == '(':                    # opening parenthesis
            stack.append('(')
        elif character == ')':                    # closing parenthesis
            while stack and stack[-1] != '(':
                output += stack.pop()
            stack.pop()                           # remove '('
        else:                                     # operator case
            while stack and stack[-1] != '(' and PRIORITY[character] <= PRIORITY[stack[-1]]:
                output += stack.pop()
            stack.append(character)

    while stack:                                  # pop remaining operators
        output += stack.pop()

    return output

expression = input()
print("infix notation: ", expression)
print("postfix notation: ", infixToPostfix(expression))
~~~
# OUTPUT
<img width="1178" height="232" alt="image" src="https://github.com/user-attachments/assets/6461a7c6-0d64-4a4f-9b8c-fc7d5e3b3c15" />

# RESULT
Thus the python program to convert infix to postfix expression has been implemented and executed successfully.
