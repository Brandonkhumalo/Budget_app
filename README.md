# Budget Category Manager with Spend Chart

This is a Python project that models budget management by creating multiple spending categories and visualizing spending distribution using a text-based bar chart.

## 📌 Features

- Create categories like **Food**, **Clothing**, or **Entertainment**.
- Deposit and withdraw money from categories.
- Transfer funds between categories.
- Track all transactions in a category-specific ledger.
- Generate a **spending chart** to visualize percentage-based expenditures across categories.

## ✅ Functional Requirements

The project includes:

- `Category` class with the following methods:
  - `deposit(amount, description="")`
  - `withdraw(amount, description="")`
  - `get_balance()`
  - `transfer(amount, other_category)`
  - `check_funds(amount)`
  - `__str__()` for a formatted output of the ledger

- `create_spend_chart(categories)` function:
  - Displays a vertical bar chart of percent-based withdrawals per category.
  - Rounded down to the nearest 10%.
  - Categories are printed vertically below the chart.

## 📄 Example Usage

```python
food = Category("Food")
clothing = Category("Clothing")
entertainment = Category("Entertainment")

food.deposit(1000, "Initial deposit")
food.withdraw(150.75, "Groceries")
food.withdraw(50, "Restaurant")

clothing.deposit(500, "Initial deposit")
clothing.withdraw(100.25, "Jeans and shoes")

entertainment.deposit(300, "Initial deposit")
entertainment.withdraw(120, "Concert tickets")

food.transfer(50, entertainment)

print(food)
print(create_spend_chart([food, clothing, entertainment]))
