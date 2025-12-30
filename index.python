import random

def display_hangman(tries):
     #Display different stages of hangman based on number of tries left
    stages = [
        """
           ------
           |    |
           |    O
           |   /|\\
           |   / \\
           |
        """,
        """
           ------
           |    |
           |    O
           |   /|\\
           |   /
           |
        """,
        """
           ------
           |    |
           |    O
           |   /|\\
           |
           |
        """,
        """
           ------
           |    |
           |    O
           |   /|
           |
           |
        """,
        """
           ------
           |    |
           |    O
           |    |
           |
           |
        """,
        """
           ------
           |    |
           |    O
           |
           |
           |
        """,
        """
           ------
           |    |
           |
           |
           |
           |
        """
    ]
    return stages[tries]

def get_word():
     #Get a random word from the list
    words = ['python', 'hangman', 'computer', 'programming','keyboard', 'mouse', 'developer', 'algorithm','nakshatra','blockchain']
    return random.choice(words).upper()  #takes random value and converts to upper case

def play_hangman():
    word = get_word()
    word_letters = set(word)  # Letters in the word
    alphabet = set('ABCDEFGHIJKLMNOPQRSTUVWXYZ')
    used_letters = set()  # Letters the user has guessed
    
    lives = 6
    
    
    while len(word_letters) > 0 and lives > 0:
        print('\n' + '='*40)
        print(display_hangman(lives))
        
        # Show current progress
        word_list = [letter if letter in used_letters else '_' for letter in word]
        print('Current word:', ' '.join(word_list))
        print('Lives left:', lives)
        print('Used letters:', ' '.join(sorted(used_letters)))
        
        # Get user input
        user_letter = input('Guess a letter: ').upper()
        
        # Validate input
        if user_letter in alphabet - used_letters:
            used_letters.add(user_letter)
            
            if user_letter in word_letters:
                word_letters.remove(user_letter)
                print(f'Good guess! {user_letter} is in the word.')
            else:
                lives -= 1
                print(f'Oops! {user_letter} is not in the word.')
                
        elif user_letter in used_letters:
            print('You already guessed that letter. Try again!')
        else:
            print('Invalid input. Please enter a single letter (A-Z).')
    
    # Game over
    print('\n' + '='*40)
    print(display_hangman(lives))
    
    if lives == 0:
        print(f'Game Over! The word was: {word}')
    else:
        print(f'Congratulations! You guessed the word: {word}')

def main():
    
    print('='*40)
    print('WELCOME TO HANGMAN!')
    print('='*40)
    print('Try to guess the word before the hangman is complete.')
    print('You have 6 lives. Good luck!\n')
    
    while True:
        play_hangman()
        
        play_again = input('\nDo you want to play again? (yes/no): ').lower()
        if play_again != 'yes':
            print('\nThanks for playing! Goodbye!')
            break

if __name__ == "__main__":
    main()
