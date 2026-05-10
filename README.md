# SciBot — AI Science Experiment Recommender ⚗️

SciBot is a full-stack AI-powered web application designed to recommend, explain, and guide users through educational science experiments. Built with a stunning dark/light futuristic laboratory aesthetic, it features a personalized streaming chatbot, a curated experiment explorer, and an interactive ingredient lab.

## 🚀 Features

### 1. Personalized Chatbot (`/`) & Session History
- **Session Sidebar:** Features a persistent sidebar that saves recent chat sessions (locally). Users can effortlessly switch between past conversations or start new ones.
- **Optional Preferences:** Features a clean, non-intrusive "Optional Preferences" bar above the chat. Users can select their **Grade Level** (6-8, 9-10, 11-12, or College) and **Subject Interest** (Physics, Chemistry, Biology) at any time.
- **Adaptive Difficulty Intelligence:** The AI automatically maps user grades to explicit pedagogical profiles (Beginner, Intermediate, Advanced), adjusting terminology, procedural complexity, and analogy depth accordingly. 
- **Real-Time Streaming:** Streams responses seamlessly from the **Groq API** using the `llama-3.3-70b-versatile` model.
- **Dynamic UI:** Features a chat window that auto-expands, distinct user/bot bubbles, glowing inputs, and a sticky navigation bar for easy access.

### 2. Experiment Explorer & Detail Pages (`/explorer`)
- **Curated Grid:** A visually appealing grid of curated science experiments with category-coded glowing borders.
- **Interactive Cards:** Hover animations, emoji scaling, and category/difficulty badges.
- **Dedicated Detail Page:** Clicking an explorer card opens a rich, interactive detail page (`/experiment/<id>`) in a new tab.

### 3. Immersive Guided Mode (`/guided-experiment`)
- **Actionable Chat:** When the Chatbot generates a full experiment, a "▶ Start Guided Mode" button automatically injects into the UI.
- **Step-by-Step UI:** Opens a beautiful, dedicated tab that extracts and parses the AI's response into an interactive checklist.
- **Progress Tracking:** Interactive "✓ Done" buttons track completion percentage with a satisfying sticky progress bar.
- **Resilient Parsing Engine:** Robust frontend regex parsing correctly structures generic AI Markdown into materials, safety, and step-by-step arrays, handling varied list formats gracefully.

### 4. Ingredient Lab (`/ingredient-lab`)
- **Animated Beaker:** Playful, pure-CSS animated bubbling beaker illustration.
- **Multi-Experiment Carousel:** Generates exactly **4 creative, non-repetitive experiments** based on materials you have at home.
- **Shuffle UI:** Features a bottom shuffle bar with a "Next Experiment" button and interactive indicator dots to cycle through generated suggestions.

## 🎨 UI/UX Highlights
- **Cross-Tab Theme Synchronization:** Persistent theme switching via the 🌙 / ☀️ navbar icon. Changes trigger `storage` events, updating all open SciBot tabs in real-time.
- **Inline Preferences:** Easily editable dropdowns for grade and subject that immediately affect future AI responses.
- **Sticky Navigation:** The global navbar remains visible during scroll for superior navigation.
- **Glassmorphism Aesthetic:** Deep navy backgrounds, neon accents, and frosted glass effects across all modals and headers.

## 🛠️ Tech Stack

- **Backend:** Python, Flask
- **Frontend:** HTML5, Vanilla JavaScript, Custom CSS (Vanilla)
- **AI Integration:** Groq Python SDK (Model: `llama-3.3-70b-versatile`)
- **State Management:** `localStorage` for themes/sessions, `sessionStorage` for cross-page payload data.

## 📂 Project Structure

```text
science-recommender/
├── app.py                 # Main Flask application, API endpoints, and System Prompts
├── .env                   # Environment variables (API Key)
├── requirements.txt       # Python dependencies
├── static/
│   ├── css/
│   │   └── style.css      # Design system, sticky layouts, and animations
│   └── js/
│       └── main.js        # Onboarding, streaming, carousel logic, and theme sync
└── templates/
    ├── base.html          # Global layout with sticky navbar
    ├── index.html         # Chatbot & Onboarding UI
    ├── explorer.html      # Experiment grid UI
    ├── experiment_detail.html # New! Dedicated experiment instruction page
    └── ingredient_lab.html# Material-based experiment generator UI
```

## ⚙️ Setup and Installation

1. **Clone the repository** (or navigate to the project directory).

2. **Create a virtual environment (optional but recommended):**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows use: venv\Scripts\activate
   ```

3. **Install Dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

4. **Configure Environment Variables:**
   - Open the `.env` file in the root directory.
   - Replace the placeholder with your actual Groq API key:
     ```env
     GROQ_API_KEY=gsk_your_actual_api_key_here
     ```

5. **Run the Application:**
   ```bash
   python app.py
   ```

6. **Access the App:**
   - Open your web browser and navigate to `http://127.0.0.1:5000`

