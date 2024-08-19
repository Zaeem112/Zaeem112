from datetime import datetime

def get_user_dob():
    dob_input = input("Enter your Date of Birth (YYYY-MM-DD): ")
    try:
        dob = datetime.strptime(dob_input, "%Y-%m-%d")
        return dob
    except ValueError:
        print("Invalid format. Please enter the date in YYYY-MM-DD format.")
        return get_user_dob()

def calculate_age(dob):
    today = datetime.today()
    age = today.year - dob.year
    if (today.month, today.day) < (dob.month, dob.day):
        age -= 1
    return age

def display_age():
    dob = get_user_dob()
    age = calculate_age(dob)
    print(f"You are {age} years old.")

# Run the age calculator
display_age()
