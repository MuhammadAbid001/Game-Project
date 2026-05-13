# Game-Project
This project is a simple Number Logic Game where the system generates a random number and the user tries to guess it
import random


def generate_secret_number():
    return random.randint(1, 50)

def check_guess(guess, secret_num):
    if guess < secret_num:
        return "Too low! Guess higher."
    elif guess > secret_num:
        return "Too high! Guess lower."
    else:
        return "correct"

def calculate_score(score):
    return max(score, 0)

def play_game():
    print("===================================")
    print(" Welcome to the Number Logic Game ")
    print("===================================")

    print("I picked a number between 1 and 50.")
    print("Can you guess it?\n")

    secret_num = generate_secret_number()

    tries = 0
    score = 100

    while True:

        guess = input("Enter your guess: ")

        # Input validation
        if not guess.isdigit():
            print("Invalid input! Please enter a number.\n")
            continue

        guess = int(guess)

        tries += 1
        score -= 5

        result = check_guess(guess, secret_num)

        if result == "correct":
            print(f"\nCongratulations! You guessed the number {secret_num}")
            print(f"Total tries: {tries}")
            print(f"Final score: {calculate_score(score)} points")
            break

        else:
            print(result)

        # Motivation message every 3 tries
        if tries % 3 == 0:
            print("Keep going! You can do it.\n")


# Run the game
play_game()
