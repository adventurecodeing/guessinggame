import random

def guess_the_number():
    print("Welcome to Guess the Number!")
    lower_bound = 1
    upper_bound = 100
    secret_number = random.randint(lower_bound, upper_bound)
    attempts = 10

    print(f"I have selected a number between {lower_bound} and {upper_bound}.")
    print(f"You have {attempts} attempts to guess the number correctly.")

    while attempts > 0:
        try:
            guess = int(input("Enter your guess: "))
            if guess < lower_bound or guess > upper_bound:
                print(f"Please guess a number between {lower_bound} and {upper_bound}.")
                continue

            if guess < secret_number:
                print("Too low!")
            elif guess > secret_number:
                print("Too high!")
            else:
                print("Congratulations! You guessed the number correctly.")
                break

            attempts -= 1
            print(f"You have {attempts} attempts remaining.")

            if attempts == 0:
                print(f"Sorry, you've run out of attempts. The number was {secret_number}.")
        except ValueError:
            print("Please enter a valid integer.")

# Run the game
guess_the_number()
