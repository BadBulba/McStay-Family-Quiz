# Ultimate Trivia Quest

A fully featured, themed trivia application built with HTML, Tailwind CSS, and JavaScript. This project features multiple quest lines, visual and audio-based questions, persistent score-tracking, and a "Final Boss" encounter.

## 🚀 Getting Started

To run this project, simply open `index.html` in your web browser. 

**Note:** Since this project uses `fetch()` to load JSON data, you may need to run it through a local development server (like the "Live Server" extension in VS Code) if it is not loading properly directly from the file system.

## 📁 Project Structure

* `index.html`: The core game engine and UI.
* `patrick_questions.json`, `hannah_questions.json`, `jillian_questions.json`: The data source for each hero's quest.
* `/images`: Folder containing all visual assets (PNG/JPG/WebP).
* `/sounds`: Folder containing all audio clips and the background music (MP3).

## 🎓 Tutorial: How to Add Questions

To add new content, edit the relevant `.json` file. Use the following structure:

### 1. Text Question
```json
{
  "question": "Your question text here?",
  "difficulty": "Easy",
  "answers": [
    { "text": "Wrong Answer", "correct": false },
    { "text": "Correct Answer", "correct": true },
    { "text": "Wrong Answer", "correct": false },
    { "text": "Wrong Answer", "correct": false }
  ]
}
```

###2. Visual Question

Add an imageSrc field. Ensure the file is inside the /images folder.
```JSON

{
  "question": "Identify this item:",
  "imageSrc": "images/filename.png",
  "difficulty": "Medium",
  "answers": [
    { "text": "Correct Answer", "correct": true },
    { "text": "Wrong Answer", "correct": false },
    { "text": "Wrong Answer", "correct": false },
    { "text": "Wrong Answer", "correct": false }
  ]
}
```
###3. Audio Question

Add an audioSrc field. Ensure the file is inside the /sounds folder.
```JSON

{
  "question": "Name this sound effect:",
  "audioSrc": "sounds/filename.mp3",
  "difficulty": "Hard",
  "answers": [
    { "text": "Wrong Answer", "correct": false },
    { "text": "Wrong Answer", "correct": false },
    { "text": "Correct Answer", "correct": true },
    { "text": "Wrong Answer", "correct": false }
  ]
}
```
⚠️ Important Rules for Data

    Case Sensitivity: Filenames must match exactly (e.g., Zidane.png is not zidane.png).

    Correctness: Each question must contain exactly one "correct": true answer.

    Format: If you add a new JSON file for a new hero, you must update the loadAllQuizData function in index.html to fetch the new file.

🛠️ Tech Stack

    Frontend: Tailwind CSS

    Logic: Vanilla JavaScript

    Storage: localStorage (for persistent scores)
