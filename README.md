# calculator
from art import logo
#add
def add(n1, n2):
  return n1+n2

#subtcrat
def sub(n1, n2):
  return n1-n2

#multiply
def mult(n1, n2):
  return n1*n2

#divide
def divid(n1, n2):
  return n1/n2

operations = {
  "+":add,
  "-":sub,
  "*":mult,
  "/":divid
}

def calculator():
  print(logo)
  num1 = float(input("What is the first number? "))
  for symbol in operations:
    print(symbol)
  should_countinue = True
  
  while should_countinue:
    operation_symbol = input("Pick an operation: ")
    num2 = float(input("What is the next number? "))
    calculation_function = operations[operation_symbol]
    answer = calculation_function(num1, num2) 
    
    print(f"{num1} {operation_symbol} {num2} = {answer}")
    
    if input(f"Type 'y' to continue to calculating with {answer}, type 'n' to start new calculation. ") == 'y':
      num1=answer
    else:
      should_countinue = False
      calculator()

calculator() 
