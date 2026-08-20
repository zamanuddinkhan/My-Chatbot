# AI Chatbot

A simple AI chatbot web application that allows users to communicate with an AI through a clean web interface.

The project uses **Python and Flask** for the backend, **HTML, CSS, and JavaScript** for the frontend, **PostgreSQL** for database storage, and an **LLM API** to generate AI responses.

## Features

* 💬 Chat with an AI assistant
* 📝 Send and receive messages in real time
* 🧠 AI-generated responses using an LLM API
* 👤 User-friendly chat interface
* 💾 Store chat and message data in PostgreSQL
* 🔐 Environment variables for API keys and sensitive configuration
* 📱 Responsive frontend
* ⚡ Flask-based REST API

## Tech Stack

### Frontend

* HTML5
* CSS3
* JavaScript

### Backend

* Python
* Flask
* Flask REST API

### Database

* PostgreSQL

### AI

* Large Language Model (LLM) API

## Project Structure

```text
ai-chatbot/
│
├── backend/
│   ├── app.py
│   ├── routes/
│   │   └── chat.py
│   ├── models/
│   │   └── chat.py
│   ├── services/
│   │   └── ai_service.py
│   └── database.py
│
├── frontend/
│   ├── index.html
│   ├── css/
│   │   └── style.css
│   └── js/
│       └── script.js
│
├── .env
├── .gitignore
├── requirements.txt
└── README.md
```

> The folder structure can be changed depending on the final implementation.

## How the Project Works

```text
User
  ↓
Chat Interface
  ↓
JavaScript
  ↓
Flask Backend
  ↓
LLM API
  ↓
AI Response
  ↓
Flask Backend
  ↓
Chat Interface
```

When a user sends a message:

1. The user enters a message in the chatbot.
2. JavaScript sends the message to the Flask backend.
3. Flask processes the request.
4. The backend sends the message to the LLM API.
5. The AI generates a response.
6. Flask sends the response back to the frontend.
7. The response is displayed in the chat window.
8. Chat information can be stored in PostgreSQL.

## Requirements

Before running the project, install:

* Python 3.10+
* PostgreSQL
* Git
* A code editor such as VS Code
* An API key for your selected LLM provider

## Installation

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/ai-chatbot.git
```

Move into the project directory:

```bash
cd ai-chatbot
```

### 2. Create a Virtual Environment

Windows:

```bash
python -m venv venv
```

Activate it:

```bash
venv\Scripts\activate
```

Linux/macOS:

```bash
python3 -m venv venv
source venv/bin/activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

## Environment Variables

Create a `.env` file in the project root:

```env
FLASK_APP=backend/app.py
FLASK_ENV=development

DATABASE_URL=postgresql://username:password@localhost:5432/ai_chatbot

LLM_API_KEY=your_api_key_here
```

Replace the placeholder values with your actual configuration.

**Do not upload your `.env` file to GitHub.**

Add it to `.gitignore`:

```gitignore
.env
venv/
__pycache__/
*.pyc
```

## Database Setup

Create a PostgreSQL database:

```sql
CREATE DATABASE ai_chatbot;
```

Configure the database connection in your application using the `DATABASE_URL` environment variable.

The database can be used to store information such as:

* Users
* Conversations
* Messages
* Message timestamps

## Running the Application

Activate the virtual environment first.

Then start the Flask server:

```bash
python backend/app.py
```

The application will normally be available at:

```text
http://127.0.0.1:5000
```

Open the address in your browser.

## API Example

The frontend can send a request to the backend:

```http
POST /api/chat
```

Example request:

```json
{
  "message": "What is machine learning?"
}
```

Example response:

```json
{
  "response": "Machine learning is a branch of artificial intelligence..."
}
```

## Example Chat

```text
User:
What is Python?

AI:
Python is a high-level programming language known for its
simple syntax and wide range of applications.
```

## Security

The project should follow these security practices:

* Never expose API keys in frontend JavaScript.
* Store secrets in environment variables.
* Add `.env` to `.gitignore`.
* Validate user input on the backend.
* Use secure database credentials.
* Use HTTPS when deploying the application.
* Implement authentication before storing private user conversations.

## Future Improvements

Possible future improvements include:

* User registration and login
* Multiple conversations
* Chat history
* Delete conversations
* Streaming AI responses
* Markdown support
* Code highlighting
* File uploads
* Voice input
* Voice output
* Dark mode
* Mobile optimization
* Conversation search
* Deployment to a cloud platform

## Screenshots

Add screenshots of the chatbot interface here after completing the frontend.

```text
screenshots/
├── home.png
├── chat.png
└── login.png
```

Example:

```markdown
![Chatbot Interface](screenshots/chat.png)
```

## Troubleshooting

### API key error

Check that your `.env` file contains the correct API key.

### Database connection error

Make sure PostgreSQL is running and that the database credentials are correct.

### Module not found

Activate your virtual environment and run:

```bash
pip install -r requirements.txt
```

### Port already in use

Run Flask on another port or stop the application currently using port `5000`.

## Development

To contribute to the project:

```bash
git checkout -b feature/new-feature
```

Make your changes, then:

```bash
git add .
git commit -m "Add new feature"
git push origin feature/new-feature
```

Create a pull request on GitHub.
