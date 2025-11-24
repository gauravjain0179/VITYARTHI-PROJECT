# Mood-Based Music Recommender

**Author:** Gaurav Jain (25BET10044)
**For:** Vityarthi Project



## Overview
This project is a simple, offline Python-based system that recommends songs based on the user's mood. It uses a question-based input system and a rule-based AI scoring method to detect emotions and generate curated playlists. No external installations, API keys, or internet connection are required.

## Features
* **Completely Offline:** Works without an internet connection.
* **Interactive Questionnaire:** Mood detection based on user answers.
* **Rule-Based AI:** Uses a scoring algorithm to determine the dominant mood.
* **Smart Playlist Generation:** Randomly selects songs from a predefined local database.
* **History Tracking:** Automatically saves user sessions to a JSON file.
* **Modular Code:** Clean structure separated into data, logic, and storage.

## Project Structure
* mood_music_recommender.py (Main application script)
* music_history.json (Stores user session history - Auto-created)
* README.md (Project documentation)

## How It Works
1. **Input:** The user answers mood-related questions (e.g., "Do you feel energetic?").
2. **Scoring:** The system assigns points to categories like Happy, Sad, Relax, Energetic, and Focus.
3. **Detection:** The algorithm compares scores; the highest score determines the current mood.
4. **Recommendation:** A playlist is generated from the internal database matching the detected mood.
5. **Storage:** The session (Name, Mood, Score, Playlist, Time) is saved to the history file.

## How to Run
1. **Prerequisites:** Ensure you have Python 3 installed.
2. **Download:** Download the project folder.
3. **Run the script:**
   Open your terminal or command prompt and run:
   python main.py
4. **Follow Instructions:** Enter numbers as prompted (1 for NO, 2 for YES).

## Technologies Used
* **Python 3:** Core programming language.
* **JSON:** For lightweight, persistent data storage.
* **Datetime:** For timestamping user sessions.
* **Random:** For shuffling and selecting songs.

## Data Storage
User history is stored in a JSON file, including:
* User Name
* Detected Mood
* Mood Score
* Recommended Playlist
* Timestamp

## Design Decisions
* **Question-Based Detection:** Chosen for simplicity and ease of use in offline environments.
* **JSON Storage:** Selected over SQL databases to keep the project lightweight and portable.
* **Internal Music List:** Removes the dependency on Spotify/YouTube APIs, ensuring the project works 100% offline.

## Future Enhancements
* GUI Interface using Tkinter.
* Music autoplay functionality.
* Sentiment analysis from user text input.
* Machine learning-based mood prediction.
