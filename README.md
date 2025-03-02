file = open("equations.txt", "a")
# Prompt user to choose if they would like to perform a calculation
perform_cal = input("Would you like to perform a calculation: Yes or No?").upper()

while (perform_cal != "YES") and (perform_cal != "NO"):
  perform_cal = input("Would you like to perform a calculation: Yes or No?").upper()
  
  if perform_cal == "NO":
    break

  elif perform_cal == "YES":
    
    break
 
    
def add(x, y):  # Function to add two numbers
  
  
  return x + y


def subtract(x, y):  # Function to subtract two numbers
  
  
  return x - y


def multiply(x, y):  # Function to multiply two numbers
  
  
  return x * y



def divide(x, y):  # Function to divide two numbers
  
  
  try:
      return x / y
  except ZeroDivisionError:
      return "Division by zero\n"  # This prints message if the number is divide by zero

# Create a file in write mode

while perform_cal == "YES":
    try:
        # Try to read an integer input from the user and store it in variable "a."
        num1 = int(input("Input first number: "))
        # If successful, break out of the loop and continue with the next code.
        break
    except ValueError:
        # If the input is not a valid integer, an exception (ValueError) is raised.
        # In that case, print an error message and prompt the user to try again.
        print("\nThis is not a number. Try again...")
        print()
    
while perform_cal == "YES":
    try:
        # Try to read an integer input from the user and store it in variable "a."
        num2 = int(input("Input second number: "))
        # If successful, break out of the loop and continue with the next code.
        break
    except ValueError:
        # If the input is not a valid integer, an exception (ValueError) is raised.
        # In that case, print an error message and prompt the user to try again.
        print("\nThis is not a number. Try again...")
        print()
if perform_cal == "YES":
  operator = input("Enter operator: ")

# If else statement to print the answer for the given operator
# If-else statement to read numbers and operator
  if operator in ('+', '-', '*', '/'):
      if operator == '+':
          print(add(num1, num2), "\n")

      elif operator == '-':
          print(subtract(num1, num2), "\n")

      elif operator == '*':
          print(multiply(num1, num2), "\n")

      elif operator == '/':
            
          print(divide(num1, num2), "\n")
      
  elif (operator != '+') and  (operator != '-') and (operator != '*') and (operator != '/'):
        print("invalid operator!")
          
  with open('equations.txt', 'a+') as eq:    
        eq.write(str(num1)+" "+operator+" "+str(num2)+"\n")
  
# Prompt user to choose if they would like to print calculations
print_cal = input("Would you like to print calculations, Yes or No?").upper()

while (print_cal != "YES") and (print_cal != "NO"):
  print_cal = input("Would you like to print calculations, Yes or No?").upper()
  
if print_cal == "NO":
  print("Goodbye!")
  exit()
  
elif print_cal == "YES":

    f = None
try:
  doc = input("Enter file you would like to print from: ").lower()
  f = open(doc, "r")
  lines = f.readlines()
  print("\n".join(lines)) # Prints all calculations stored in file
      
except FileNotFoundError as error:
        print("The file that you are trying to open does not exist")
        print(error) # If condition is not met, error message is raised
finally:
        if f is not None:
          f.close()
