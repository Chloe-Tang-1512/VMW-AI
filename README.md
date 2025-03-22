PM - Chloe Tang: chloetang1122@gmail.com
VPM - Kevin H:  kevkevh11@gmail.com
Developer - Alice: alice6688li@gmail.com

# Definition Guessing Game

Welcome to the **Definition Guessing Game**, a fun and educational game where you test your knowledge of word definitions! This game fetches definitions from the Dictionary API and challenges you to choose the correct definition from a list of options.

---

## Table of Contents
- [How to Play](#how-to-play)
- [Features](#features)
- [Requirements](#requirements)
- [Installation](#installation)
- [Usage](#usage)
- [Example Gameplay](#example-gameplay)
- [License](#license)

---

## How to Play
1. The game will display a random word.
2. You will be presented with three possible definitions:
   - One correct definition fetched from the Dictionary API.
   - Two fake definitions.
3. Your task is to choose the correct definition by entering the corresponding number (1, 2, or 3).
4. The game will tell you if your choice was correct or incorrect and display the correct definition if you were wrong.

---

## Features
- Fetches real definitions from the [Dictionary API](https://dictionaryapi.dev/).
- Includes a predefined list of random words.
- Provides a mix of real and fake definitions for a fun challenge.
- Simple and interactive gameplay.

---

## Requirements
- Python 3.x
- Internet connection (to fetch definitions from the Dictionary API)

---

## Installation
1. Clone this repository or download the `dictionary.py` file.
2. Ensure you have Python 3.x installed on your system.
3. Install the required Python modules:
   - If using the `requests` library, install it with:
     ```bash
     pip install requests
     ```
   - Alternatively, use the built-in `urllib` module (no installation required).

---

## Usage
1. Run the game script:
   ```bash
   python dictionary.py
