# Flask Guess the Number Game 🎮

Welcome to the **Flask Guess the Number** game! This is a simple web application where the user tries to guess a random number between 0 and 9.

## 🛠️ Features

- **Home Route (`/`)**: Displays an introduction to the game with a GIF.
- **Guess Route (`/<int:guess>`)**: Takes a guess as an integer parameter and tells you whether the guess is too high, too low, or correct, with a corresponding GIF.

## 🚀 Installation

Follow these steps to get your app up and running.

### Prerequisites

- **Python**: Ensure Python is installed on your system. You can download it from [python.org](https://www.python.org/).
- **Flask**: Install Flask using pip.

```bash
pip install flask
```
---
## Setup
1. Save the following Python code in a file called guess_number.py:
```python
from flask import Flask
import random

random_number = random.randint(0, 9)
print(random_number)

app = Flask(__name__)

@app.route('/')
def home():
    return "<h1>Guess a number between 0 and 9</h1>" \
           "<img src='https://media.giphy.com/media/3o7aCSPqXE5C6T8tBC/giphy.gif'/>"

@app.route("/<int:guess>")
def guess_number(guess):
    if guess > random_number:
        return "<h1 style='color: purple'>Too high, try again!</h1>" \
               "<img src='https://media.giphy.com/media/3o6ZtaO9BZHcOjmErm/giphy.gif'/>"

    elif guess < random_number:
        return "<h1 style='color: red'>Too low, try again!</h1>"\
               "<img src='https://media.giphy.com/media/jD4DwBtqPXRXa/giphy.gif'/>"
    else:
        return "<h1 style='color: green'>You found me!</h1>" \
               "<img src='https://media.giphy.com/media/4T7e4DmcrP9du/giphy.gif'/>"

if __name__ == "__main__":
    app.run(debug=True)
```
2. Set the FLASK_APP environment variable: For Windows (PowerShell):
```bash
$env:FLASK_APP = "guess_number.py"
```
For macOS/Linux:
```bash
export FLASK_APP=guess_number.py
```
3. Run the Flask development server:
```bash
python -m flask run
```
Now, visit http://127.0.0.1:5000/ in your browser to start the game. You can then try guessing numbers between 0 and 9 by entering http://127.0.0.1:5000/<your_guess> (e.g., http://127.0.0.1:5000/5).
---
## ⚙️ Environment Configuration
If you want to run this app in production, it's recommended to set up a production-ready server like Gunicorn or uWSGI.
---
## 📚 Learn More
- Flask Documentation: https://flask.palletsprojects.com/
- Python Documentation: https://docs.python.org/
---
## 💡 License
This project is open-source and available under the MIT License.
---
Happy coding! 🎉
