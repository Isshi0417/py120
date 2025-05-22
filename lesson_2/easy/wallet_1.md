# Wallet (Part 1)

Implement a `Wallet` class that represents a wallet with a certain amount of money. You want to be able to combine (add) two wallets together to get a new wallet with the combined total amount from both wallets.

# Solution

```python
class Wallet():
    def __init__(self, amount):
        self.amount = amount

    def __add__(self,other):
        if isinstance(other, Wallet):
            return Wallet(self.amount + other.amount)
```