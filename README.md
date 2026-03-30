# Game-Project
This project is a simple Number Logic Game where the system generates a random number and the user tries to guess it
import random
print("Hey! Let's play a guessing game ")
print("I picked a number between 1 and 50. Can you guess it?")
secret_num = random.randint(1, 50)  
tries = 0
score = 100
while True:
    guess = input("Your guess: ")
   
   
   
    if not guess.isdigit():
        print("Hmm, that's not a number. Try again ")
        continue
    guess = int(guess)
    tries += 1
    score -= 5  
    if guess == secret_num:
        print(f"Yay! You got it! It was {secret_num}")
        print(f"You took {tries} tries and scored {max(score, 0)} points ")
        break
    elif guess < secret_num:
        print("Too low, guess higher ")
    else:
        print("Too high, guess lower ")
 
    if tries % 3 == 0:
        print("Keep going! You got this ")
