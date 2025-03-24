# python-week-4def calculator(num1, num2, operation):
    try:
        operations = {
            '+': num1 + num2,
            '-': num1 - num2,
            '*': num1 * num2,
            '/': num1 / num2 if num2 != 0 else "Error: Division by zero is not allowed."
        }
        
        result = operations.get(operation, "Invalid operation. Please enter +, -, *, or /.")
        return f"{num1} {operation} {num2} = {result}"
    except ValueError:
        return "Invalid input. Please enter numeric values."

def calculate_discount(price, discount_percent):
    if discount_percent >= 20:
        final_price = price - (price * discount_percent / 100)
        return final_price
    return price

def file_read_write(filename):
    try:
        with open(filename, 'r') as file:
            content = file.read()
        
        modified_content = content.upper()
        
        new_filename = "modified_" + filename
        with open(new_filename, 'w') as new_file:
            new_file.write(modified_content)
        
        return f"Modified content saved to {new_filename}"
    except FileNotFoundError:
        return "Error: The file does not exist."
    except IOError:
        return "Error: Could not read the file."

# Example function calls (Replace with user input in an interactive environment)
if __name__ == "__main__":
    print(calculate_discount(100, 25))  # Example test case
    print(calculator(10, 5, '+'))       # Example test case
    print(file_read_write("example.txt"))  # Example test case
