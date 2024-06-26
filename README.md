
def determine_winner(player_choice, computer_choice):
    if player_choice == computer_choice:
        return "It's a tie!"
    elif (player_choice == 'rock' and computer_choice == 'scissors') or \
         (player_choice == 'paper' and computer_choice == 'rock') or \
         (player_choice == 'scissors' and computer_choice == 'paper'):
        return "You win!"
    else:
        return "Computer wins!"

def main():
    choices = ['rock', 'paper', 'scissors']

    while True:
        print("\nWelcome to Rock-Paper-Scissors game!")
        print("Enter your choice: ")
        print("1. Rock")
        print("2. Paper")
        print("3. Scissors")
        print("4. Quit game")

        player_choice = input("Enter your choice (1-4): ").strip().lower()

        if player_choice == '4' or player_choice == 'quit':
            print("Thanks for playing!")
            break
        elif player_choice in {'1', 'rock'}:
            player_choice = 'rock'
        elif player_choice in {'2', 'paper'}:
            player_choice = 'paper'
        elif player_choice in {'3', 'scissors'}:
            player_choice = 'scissors'
        else:
            print("Invalid choice. Please enter 1, 2, 3, or 4.")
            continue

        computer_choice = random.choice(choices)
        print(f"\nYou chose: {player_choice}")
        print(f"Computer chose: {computer_choice}")

        result = determine_winner(player_choice, computer_choice)
        print(result)

if __name__ == "__main__":
    main()
