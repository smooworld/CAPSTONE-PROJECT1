# CAPSTONE-PROJECT1
variables and control structures
finance calculator
import math
# Telling user the type of calculator to choose and what they do accordingly
print("Choose either 'investment' or 'bond' from the menu below to proceed: \n")
print("Investment       \t - to calculate the amount of interest you'll earn on interest")
print("Bond             \t - to calculate the amount you'll have to pay on home loan \n")

# Request user to input there choice of calculator between "investment" or "bond"
calculator = input("Please enter 'investment' or enter 'bond': \n ").lower()

# If statement to ask the user the investment rate they want to calculate
# Either simple or compound
# Request user to input details for the calculation
if calculator == "investment":
    money_deposit = float(input("Please enter the amount of deposit: \n"))
    interest_rate = float(input("Please enter your interest rate (Numbers only): \n"))
    interest_rate_new = interest_rate / 100
    num_year = int(input("Please enter the number of year you plan to invest for: \n"))
    interest = input("Please choose if u want a 'simple' or 'compound' interest: \n").lower()
#
    if interest == "simple":
        sim_interest = round(money_deposit * (1 + interest_rate_new * num_year))
# Display the amount deposited, interest rate, number of year planned for investment and the total
        print(f"Amount Invested:           \t R{money_deposit} \n" +
              f"Interest Rate:             \t {interest_rate_new}% \n" +
              f"Investment period:         \t {num_year} years \n" +
              #"*" * 80 +
              f"Investment total:      \t R{sim_interest} \n" +
              "*" * 80)
    if interest == "compound":
        comp_interest = round(money_deposit * math.pow((1 + interest_rate_new), num_year))
# Display the amount deposited, interest rate, number of year planned for investment and the total
        print(f"Amount Invested:           \t R{money_deposit} \n" +
              f"Interest Rate:             \t {interest_rate_new}% \n" +
              f"Investment period:         \t {num_year} years \n" +
              # "*" * 80 +
              f"Investment total:      \t R{comp_interest} \n" +
              "*" * 80)

# Request user to input details for bond calculation on what to repay every month
if calculator == "bond":
    pres_val_house = float(input("Please enter the present value of the house: \n"))
    interest_rate_bond = float(input("Please enter the interest rate (Numbers only): \n"))
    interest_rate_bond1 = interest_rate_bond / 100
    monthly_int_rate = interest_rate_bond1 / 12
    num_months = int(input(("Please enter the number of months you plan to repay the bond: \n")))
    bond_repayment = round((monthly_int_rate * pres_val_house) / (1 - (1 + monthly_int_rate) ** (- num_months)))

# Display the value of House, monthly interest rate, number of months and the exact amount to pay back
    print(f"Value of house:            \t R{pres_val_house} \n" +
          f"Interest Rate:             \t {monthly_int_rate}% \n" +
          f"Investment period:         \t {num_months} months \n" +
          # "*" * 80
          f"Monthly repayment:         \t R{bond_repayment} \n" +
          "*" * 80)
