Mood-Based Music Recommender 



Author: Gaurav Jain (25BET10044)

For: Vityarthi Project


Overview

This project is a simple, offline Python-based system that recommends songs based on the user's mood. It uses a question-based input system and a rule-based AI scoring method to detect emotions and generate curated playlists. No external installations, API keys, or internet connection are required.


Features

Completely Offline: Works without an internet connection.

Interactive Questionnaire: mood detection based on user answers.

Rule-Based AI: Uses a scoring algorithm to determine the dominant mood.

Smart Playlist Generation: Randomly selects songs from a predefined local database.

History Tracking: Automatically saves user sessions to a JSON file.

Modular Code: Clean structure separated into data, logic, and storage.


Project Structure

mood-music-recommender/
│
├── main.py   # Main application script
├── music_history.json          # Stores user session history (Auto-created)
└── README.md                   # Project documentation


How It Works

Input: The user answers 7 mood-related questions (e.g., "Do you feel energetic?").

Scoring: The system assigns points to categories like Happy, Sad, Relax, Energetic, and Focus.

Detection: The algorithm compares scores; the highest score determines the current mood.

Recommendation: A playlist is generated from the internal database matching the detected mood.

Storage: The session (Name, Mood, Score, Playlist, Time) is saved to music_history.json.


How to Run

Prerequisites: Ensure you have Python 3.x installed.

Download: Download the project folder.

Run the script:

python main.py



Follow Instructions: Enter 1 for NO and 2 for YES when prompted.

Technologies Used

Python 3: Core programming language.

JSON: For lightweight, persistent data storage.

Datetime: For timestamping user sessions.

Random: For shuffling and selecting songs.


Data Storage

User history is stored in music_history.json in the following format:

User Name

Detected Mood

Mood Score

Recommended Playlist

Timestamp



Design Decisions

Question-Based Detection: Chosen for simplicity and ease of use in offline environments.

JSON Storage: Selected over SQL databases to keep the project lightweight and portable.

Internal Music List: Removes the dependency on Spotify/YouTube APIs, ensuring the project works 100% offline.



Future Enhancements

[ ] GUI Interface: Upgrade from CLI to a graphical interface using Tkinter.

[ ] Music Autoplay: Play songs directly using the playsound or pygame library.

[ ] Sentiment Analysis: Allow users to type how they feel and use NLP to detect mood.

[ ] Cloud Integration: Sync history with online music platforms.
