# Bank Account System

A Python-based banking system that simulates various types of bank accounts with inheritance relationships and realistic banking features.

## 📋 Overview

This system models a collection of bank account types with different features and behaviors:

- **Basic Bank Account**: Standard account with deposit, withdrawal, and transfer capabilities
- **Interest Rewards Account**: Provides interest bonuses on deposits
- **Savings Account**: A specialized interest account with withdrawal fees and monthly limits
- **Checking Account**: Offers overdraft protection with fees

## ✨ Features

- **Transaction History**: Records all account activities
- **Exception Handling**: Custom exceptions for insufficient funds
- **Interest Calculation**: Both on deposits and monthly balances
- **Fee System**: Transaction fees for certain account types
- **Account Limits**: Monthly withdrawal limits for savings accounts
- **Overdraft Protection**: Allows withdrawals beyond balance with fee
- **Owner Information**: Tracks account ownership

## 🏗️ Class Hierarchy

```
BankAccount
├── InterestRewardsAcct
│   └── SavingsAcct
└── CheckingAccount
```


## 🚀 Usage Example

```python
# Create accounts
john_checking = CheckingAccount(1000, "Checking", "John Smith")
john_savings = SavingsAcct(5000, "Savings", "John Smith")
mary_rewards = InterestRewardsAcct(2000, "Rewards", "Mary Johnson")

# Make deposits
john_checking.deposit(500)
john_savings.deposit(1000)  # With interest bonus

# Make withdrawals
john_checking.withdraw(1200)  # Using overdraft
john_savings.withdraw(100)  # With fee

# Transfer between accounts
john_checking.transfer(200, john_savings)

# Apply monthly interest
mary_rewards.apply_monthly_interest()

# View transaction history
john_checking.show_transaction_history()
```

## 📝 API Documentation

### BankAccount
- `__init__(initial_amount, acct_name, owner_name)`: Creates a new account
- `deposit(amount)`: Adds funds to the account
- `withdraw(amount)`: Removes funds from the account
- `transfer(amount, account)`: Moves funds to another account
- `get_balance()`: Displays current balance
- `show_transaction_history()`: Lists all account activities

### InterestRewardsAcct
- `deposit(amount)`: Adds funds with interest bonus
- `apply_monthly_interest()`: Applies periodic interest to balance

### SavingsAcct
- `withdraw(amount)`: Removes funds with fee
- `reset_monthly_withdrawals()`: Resets monthly withdrawal counter

### CheckingAccount
- `withdraw(amount)`: Supports overdraft with fees

## 🛡️ Exception Handling

The system uses a custom `BalanceException` to handle insufficient funds situations in a user-friendly way:

```python
class BalanceException(Exception):
    pass
    
# Usage example
try:
    account.withdraw(1000)
except BalanceException as error:
    print(f"Transaction failed: {error}")
```

## 🔜 Future Enhancements

- Account number generation
- PIN/password protection
- Joint account functionality
- Loan and credit card accounts
- Currency conversion
- Transaction date/time tracking
- Automated scheduled transfers


