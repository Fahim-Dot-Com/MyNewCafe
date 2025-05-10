# Let's start a coffee shop together!!
# We're going to build a coffee shop using some new Python programming concepts!!

print("Hello, welcome to Fahim's Coffee!!!!!!!!!!!!!!")

name = input("What is your name?\n")

if name.lower() == "ben":
    print("You're not welcome here, evil Ben!! Get out!!")
    exit()
else:
    print(f"Hello {name}, thank you so much for coming in today.\n")

# Menu and prices
menu = {
    "Black Coffee": 0.99,
    "Espresso": 1.99,
    "Latte": 2.99,
    "Cappuccino": 3.99
}

total_cost = 0  # Keep track of the total order cost

# Start order loop
while True:
    print(f"{name}, here is our menu:")
    for item, price in menu.items():
        print(f"- {item}: ${price}")

    order = input("\nWhat would you like to order?\n").title()

    if order not in menu:
        print("Sorry, we don't have that item. Please choose something from the menu.\n")
        continue

    # Ask for quantity
    quantity = input(f"How many {order}s would you like?\n")
    if not quantity.isdigit():
        print("Please enter a valid number.\n")
        continue

    item_total = menu[order] * int(quantity)
    total_cost += item_total

    print(f"Great choice! That will be ${item_total:.2f} for {quantity} {order}(s).")

    # Ask if they want anything else
    another = input("Would you like anything else? (yes/no)\n").lower()
    if another == "no":
        break
    elif another != "yes":
        print("I didn't understand that. Let's just finish up your order.\n")
        break

# Final receipt
print(f"\nThank you, {name}! Your total bill is: ${total_cost:.2f}")
print("Have a lovely day! Come again soon ☕")
