import random

def guessing_game():
    print("Welcome to the Number Guessing Game!")
    print("You have to guess the number I'm thinking of.")
    print("Hints will help you get closer. Good luck!")

    # Define the range of numbers and choose a random number
    lower_bound = 1
    upper_bound = 100
    number_to_guess = random.randint(lower_bound, upper_bound)
    attempts = 0

    while True:
        try:
            user_guess = int(input(f"Enter your guess ({lower_bound}-{upper_bound}): "))
            attempts += 1
            
            if user_guess < lower_bound or user_guess > upper_bound:
                print(f"Please guess within the range {lower_bound}-{upper_bound}.")
                continue

            if user_guess < number_to_guess:
                print("Too low! Try a higher number.")
            elif user_guess > number_to_guess:
                print("Too high! Try a lower number.")
            else:
                print(f"Congratulations! You guessed the number {number_to_guess} in {attempts} attempts.")
                break
        except ValueError:
            print("Invalid input! Please enter a number.")

if __name__ == "__main__":
    guessing_game()
