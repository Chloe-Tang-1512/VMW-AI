import requests
import random

def fetch_definitions(word):
    """Fetch definitions for a given word from the Dictionary API."""
    url = f"https://api.dictionaryapi.dev/api/v2/entries/en/{word}"
    try:
        response = requests.get(url)
        response.raise_for_status()
        data = response.json()
        definitions = []
        for meaning in data[0]["meanings"]:
            for definition in meaning["definitions"]:
                definitions.append(definition["definition"])
        return definitions
    except Exception as e:
        print(f"Error fetching definitions for '{word}': {e}")
        return []

def get_random_word():
    """Return a random word from a predefined list."""
    words = ["hello", "world", "python", "game", "dictionary", "challenge", "random", "guess", "definition", "program"]
    return random.choice(words)

def play_game():
    """Main game logic."""
    print("Welcome to the Definition Guessing Game!")
    print("You will be given a word and three possible definitions.")
    print("Your task is to choose the correct definition. Good luck!\n")

    # Get a random word
    word = get_random_word()
    print(f"The word is: {word}\n")

    # Fetch definitions for the word
    correct_definitions = fetch_definitions(word)
    if not correct_definitions:
        print("Could not fetch definitions. Please try again later.")
        return

    # Select the correct definition and generate fake ones
    correct_definition = random.choice(correct_definitions)
    fake_definitions = [
        "A type of fruit that grows in tropical climates.",
        "A tool used for cutting wood.",
        "A mythical creature from ancient folklore."
    ]
    options = [correct_definition] + random.sample(fake_definitions, 2)
    random.shuffle(options)

    # Display the options
    print("Choose the correct definition:")
    for i, option in enumerate(options, 1):
        print(f"{i}. {option}")

    # Get the player's choice
    try:
        choice = int(input("\nEnter the number of your choice: "))
        if choice < 1 or choice > 3:
            print("Invalid choice. Please enter a number between 1 and 3.")
        elif options[choice - 1] == correct_definition:
            print("Correct! Well done!")
        else:
            print(f"Wrong! The correct definition was: {correct_definition}")
    except ValueError:
        print("Invalid input. Please enter a number.")

if __name__ == "__main__":
    play_game()
