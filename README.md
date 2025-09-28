# cafe-management-system
menu = {
    "aloo tikki": 40,
    "pav bhaji": 80,
    "pani puri": 30,
    "bhel puri": 60,
    "vada pau": 70
}

print("Welcome to Bukaad")
print("-------- MENU --------")
for item, price in menu.items():
    print(f"{item}: {price}")

bill = 0
purchased_items = {}

while True:
    your_order = input("Enter your order: ")
    if your_order in menu:
        quantity = int(input("How many pieces you want: "))
        bill += (quantity * menu[your_order])
        
        # If item already purchased, add more quantity
        if your_order in purchased_items:
            purchased_items[your_order] += quantity
        else:
            purchased_items[your_order] = quantity

        k = input("Would you like to add more items? (yes/no): ")
        if k.lower() == "no":
            break
    else:
        print("Invalid item! Please choose from menu.")

print("\n----- Your Bill -----")
for item, quantity in purchased_items.items():
    print(f"{item} x {quantity} = {menu[item] * quantity}")
print("---------------------")
print(f"Total Bill: {bill}")
