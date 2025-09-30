# Bank-account-cpp-program
#include <iostream>
using namespace std;

// Class for Bank Account
class BankAccount {
private:  
    // Private data members (cannot be accessed directly outside the class)
    string accountHolder;
    int accountNumber;
    double balance;

public:  
    // Constructor to initialize account
    BankAccount(string name, int accNo, double initialBalance) {
        accountHolder = name;
        accountNumber = accNo;
        balance = initialBalance;
    }

    // Function to deposit money (public: accessible outside class)
    void deposit(double amount) {
        if (amount > 0) {
            balance += amount;
            cout << "Deposited: " << amount << " | New Balance: " << balance << endl;
        } else {
            cout << "Invalid deposit amount!" << endl;
        }
    }

    // Function to withdraw money
    void withdraw(double amount) {
        if (amount > 0 && amount <= balance) {
            balance -= amount;
            cout << "Withdrawn: " << amount << " | New Balance: " << balance << endl;
        } else {
            cout << "Insufficient balance or invalid amount!" << endl;
        }
    }

    // Function to display account details
    void displayAccount() {
        cout << "Account Holder: " << accountHolder << endl;
        cout << "Account Number: " << accountNumber << endl;
        cout << "Balance: " << balance << endl;
    }
};

// Main function
int main() {
    // Create a BankAccount object
    BankAccount acc1("Rudra", 101, 5000.0);

    // Perform operations
    acc1.displayAccount();   // Show account details
    acc1.deposit(2000);      // Deposit money
    acc1.withdraw(1500);     // Withdraw money
    acc1.withdraw(7000);     // Try to withdraw more than balance

    return 0;
}
