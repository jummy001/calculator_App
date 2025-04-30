# calculator_App
def calculate_discount(price, discount_percent):
    if discount_percent >= 20:
        discount_amount = (discount_percent / 100) * price
        return price - discount_amount
    else:
        return price

def get_valid_float(prompt):
    while True:
        try:
            value = float(input(prompt))
            if value < 0:
                print("Please enter a positive number.")
            else:
                return value
        except ValueError:
            print("Invalid input. Please enter a numeric value.")

# Get validated user input
original_price = get_valid_float("Enter the original price of the item: ")
discount = get_valid_float("Enter the discount percentage: ")

# Calculate final price
final_price = calculate_discount(original_price, discount)

# Output result
if discount >= 20:
    print(f"Discount applied. Final price: ${final_price:.2f}")
else:
    print(f"No discount applied. Final price: ${final_price:.2f}")
