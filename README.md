class BankAccount:
    def __init__(self, account_holder, initial_balance=0):
        self.account_holder = account_holder
        self.__balance = initial_balance

    def get_balance(self):
        return self.__balance

    def deposit(self, amount):
        if amount > 0:
            self.__balance += amount
            print(f"₹{amount} deposited successfully.\n Total Balance:")
        else:
            print("Invalid deposit amount.")

    def withdraw(self, amount):
        if amount <= self.__balance:
            self.__balance -= amount
            print(f"₹{amount} withdrawn successfully.\n Remaining Balance")
        else:
            print("Insufficient balance.")

    def account_info(self):
        print(f"\n--- Account Info ---")
        print(f"Account Holder: {self.account_holder}")
        print(f"Current Balance: ₹{self.__balance}\n")


def main():
    print("=== Welcome to Kotak Mahindra Bank ===")
    name = input("Enter your name: ")
    initial = float(input("Enter initial deposit: ₹"))
    account = BankAccount(name, initial)

    while True:
        print("\nChoose an option:")
        print("1. Deposit")
        print("2. Withdraw")
        print("3. Check Balance")
        print("4. Account Info")
        print("5. Exit")

        choice = input("Enter your choice (1-5): ")

        if choice == '1':
            amt = float(input("Enter amount to deposit: ₹"))
            account.deposit(amt)
        elif choice == '2':
            amt = float(input("Enter amount to withdraw: ₹"))
            account.withdraw(amt)
        elif choice == '3':
            print(f"Current Balance: ₹{account.get_balance()}")
        elif choice == '4':
            account.account_info()
        elif choice == '5':
            print("Thank you for using Kotak Mahindra Bank. Goodbye!")
            break
        else:
            print("Invalid choice. Please select between 1-5.")

if __name__ == "__main__":
    main()
