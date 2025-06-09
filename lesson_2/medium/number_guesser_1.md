# Number Guesser

Create an object-oriented number guessing class for numbers in the range 1 to 100, with a limit of 7 guesses per game. The game should play like this:

```
game = GuessingGame()
game.play()

You have 7 guesses remaining.
Enter a number between 1 and 100: 104
Invalid guess. Enter a number between 1 and 100: 50
Your guess is too low.

You have 6 guesses remaining.
Enter a number between 1 and 100: 75
Your guess is too low.

You have 5 guesses remaining.
Enter a number between 1 and 100: 85
Your guess is too high.

You have 4 guesses remaining.
Enter a number between 1 and 100: 0
Invalid guess. Enter a number between 1 and 100: 80
Your guess is too low.

You have 3 guesses remaining.
Enter a number between 1 and 100: 81
That's the number!

You won!

game.play()

You have 7 guesses remaining.
Enter a number between 1 and 100: 50
Your guess is too high.

You have 6 guesses remaining.
Enter a number between 1 and 100: 25
Your guess is too low.

You have 5 guesses remaining.
Enter a number between 1 and 100: 37
Your guess is too high.

You have 4 guesses remaining.
Enter a number between 1 and 100: 31
Your guess is too low.

You have 3 guesses remaining.
Enter a number between 1 and 100: 34
Your guess is too high.

You have 2 guesses remaining.
Enter a number between 1 and 100: 32
Your guess is too low.

You have 1 guess remaining.
Enter a number between 1 and 100: 32
Your guess is too low.

You have no more guesses. You lost!
```

Note that a game should start a new game with a new number to guess with each call to `play`.

# Solution

```python
import random

class GuessingGame:
    def __init__(self):
        self.number = None
        self.guesses = None
        self.player_input = None
    
    def play(self):
        self.number = random.randint(1, 100)
        self.guesses = 7

        while self.guesses > 0:
            self.prompt()
            self.guess()
        
    def prompt(self):
        if self.guesses > 1:
            print(f"\nYou have {self.guesses} guesses remaining.")
        else:
            print(f"\nYou have {self.guesses} guess remaining.")

    def guess(self):
        self.player_input = input("Enter a number between 1 and 100: ")
        self.check_input()
        player_guess = int(self.player_input)
        self.check_guess(player_guess)

    def check_input(self):
        while not self.player_input.isnumeric():
                    self.player_input = input("Invalid guess. Enter a number between 1 and 100: ")

        if self.player_input.isnumeric():
            while int(self.player_input) < 1 or int(self.player_input) > 100:
                self.player_input = input("Invalid guess. Enter a number between 1 and 100: ")


    def check_guess(self, player_guess):
        if player_guess == self.number:
            print("That's the number!")
            print("\nYou won!")
            self.guesses = 0
            return
        elif player_guess > self.number:
            print("Your guess is too high.")
            self.guesses -= 1
            self.check_loss()
        else:
            print("Your guess is too low.")
            self.guesses -= 1
            self.check_loss()

    def check_loss(self):
        if self.guesses == 0:
            print(f"\nYou have no more guesses. You lost!")
            return

game = GuessingGame()
game.play()
game.play()
```