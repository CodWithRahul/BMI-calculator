# Function to calculate BMI
def calculate_bmi(weight, height):
    # BMI formula: weight (kg) / height (m)^2
    bmi = weight / (height ** 2)
    return bmi

# Function to interpret BMI value
def interpret_bmi(bmi):
    # Based on WHO standard BMI categories
    if bmi < 18.5:
        return "Underweight"
    elif 18.5 <= bmi < 24.9:
        return "Normal weight"
    elif 25 <= bmi < 29.9:
        return "Overweight"
    else:
        return "Obese"

# Main function to run the BMI calculator
def main():
    print("Welcome to the BMI Calculator")

    try:
        # Ask user to input weight and height
        weight = float(input("Enter your weight in kilograms (kg): "))
        height = float(input("Enter your height in meters (m): "))

        # Validate that inputs are positive numbers
        if weight <= 0 or height <= 0:
            print("Weight and height must be positive numbers.")
            return

        # Calculate the BMI using the function
        bmi = calculate_bmi(weight, height)

        # Get the interpretation/category of the BMI
        category = interpret_bmi(bmi)

        # Show the result to the user
        print(f"\nYour BMI is: {bmi:.2f}")  # Format BMI to 2 decimal places
        print(f"BMI Category: {category}")

    except ValueError:
        # Handle error if input is not a number
        print("Invalid input. Please enter numeric values only.")

# Entry point of the program
if __name__ == "__main__":
    main()
