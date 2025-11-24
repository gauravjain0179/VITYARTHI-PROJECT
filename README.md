# MUSIC RECCOMENDER BY MOOD
Most music applications require network and advanced connectivity and coding and advanced ML applications for detection of mood.  However beginners need a program that works offline, is easy to understand, uses basic python that generates music playlists without needing any external library THIS IS



CODE OF TTHE PROGRAM

#mood-basedmusic detector 
#by gaurav jain 25BET10044
import json
import random
from datetime import datetime
import os

#content

music_db= {
  "happy": [
    "gallan goodiyan",
    "aaj mai upar",
    "lover-taylor swift",
    "yellow-coldplay"
    ],
  "sad": [
    "maa",
    "agar tum sath ho-arijit singh",
    "daylight",
    "how soon is now-the smiths"
    ],
  "relax": [
    "kabira-pritam",
    "tumse hi-mohit chauhan",
    "sparks-coldplay",
    "video game-lanadel ray"
    ],
  "focus": [
    "bandeya re bandeya",
     "mast magan",
    "sparks"
    ],
  "energetic": [
    "believer",
    "thodi si daaru",
    "sapphire",
    "wavin flag"
    ],
  "old": [
    "lag ja gale",
    "kal chaudhvi ki raat thi"
    ],
  "romantic": [
    "i wanna be yours",
    "brooklyn baby",
    "k",
    "rang sharbaton ka"] 
    
}
#history

history_file = "music_history.json"

def load_history():
  if not os.path.exists(history_file):
    return[]
  with open(history_file, "r") as f:
    return json.load(f)
    
def save_history(entry):
  history = load_history()
  history.append(entry)
  with open(history_file, "w") as f:
    json.dump(history, f, indent=4)
    
#moodfinding

def calculate_mood_score():
  print("\n answer honestly (1 = No, 2= Yes): ")
  q1 = int(input("do you feel energetic today? "))
  q2 = int(input("do you feel calm and peaceful? "))
  q3 = int(input("do you feel sad or low? "))
  q4 = int(input("are you excited or happy? "))
  q5 = int(input("do you need to focus on your tasks? "))
  q6 = int(input("are you feeling retro? "))
  q7 = int(input("are you feeling romantic? "))
  scores = {
    "energetic": q1 + q4,
    "relax": q2,
    "sad": q3*2,
    "happy": q4,
    "focus": q5,
    "old": q6 + q2,
    "romantic": q7+ q4
   } 
  #deciding mood
   mood = max(scores, key=scores.get)
  return mood, scores[mood]
  
#generate playlist

def generate_playlist(mood,count=3):
  songs = music_db.get(mood, [])
  if len(songs) <=count:
    return songs
  return random.sample(songs, count)
  
#main finction

def main():
 print("===")
 print("MOOD MUSIC RECOMMENDER")
 print("===")

name = input("enter your name: ")
mood, score = calculate_mood_score()
playlist = generate_playlist(mood)

print("\n based on your mood, we detected: ")
print(f"--> mood: {mood.upper()} (score: {score})")
print("\n your generated playlist:")
for i, song in enumerate(playlist, 1):
  print(f"{i}. {song}")
    
    #save history
entry = {
      "name": name ,
      "mood": mood,
      "score": score,
      "playlist": playlist,
      "time": datetime.now().strftime("%Y-%m-%d %H:%M:%S")
    }
save_history(entry)
print("\nyour playlist has been saved to history.")
print("run again to build new mood patterns")
print("thank you for using")
    
    #run
if __name__ == "__main__":
   main()
