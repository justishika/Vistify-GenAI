# Vistify - AI Video Summarizer and Analyst🎥✨

![Vistify Preview](./img/logo.svg)

## 🚀 Key Features

### 1. 📝 Dual-Mode Summarization
*   **10-Point Summary**: Get the gist of any video in exactly 10 concise, numbered points. Perfect for quick consumption.
*   **In-Depth Summary**: A comprehensive, structured report with IEEE-style headings, subheadings, and bullet points. Ideal for lectures and technical content.

### 2. 💬 Interactive Q&A with RAG
*   **Chat with Video**: Ask specific questions about the video content.
*   **RAG Architecture**: Uses **TF-IDF** vectorization to retrieve the most relevant transcript chunks, ensuring answers are grounded in the video's actual content.
*   **Hallucination Prevention**: Strict prompting ensures the AI answers *only* using the provided context.

### 3. 📊 Trust & Evaluation Metrics
Every Q&A response includes real-time metrics to help you trust the AI:
*   **🔍 Retrieval Score**: How relevant the found context is to your question (Cosine Similarity).
*   **✅ Faithfulness**: How well the answer matches the retrieved context (Word Overlap/ROUGE-1).
*   **⏱️ Latency**: Time taken to generate the response.

### 4. 🧠 Deep Insights & Entity Extraction
*   **Named Entity Recognition (NER)**: Automatically identifies and categorizes People, Organizations, Locations, Dates, and more.
*   **Key Insights**: Auto-generates "Key Insights" and "Suggested Questions" to help you explore the video further.

---

## 🛠️ Tech Stack

### Frontend
*   **Core**: HTML5, CSS3 (Custom Glassmorphism Design), JavaScript (ES6+).
*   **Architecture**: MVC (Model-View-Controller) pattern for clean code separation.
*   **Build Tool**: Parcel.

### Backend
*   **Framework**: Python Flask (REST API).
*   **Server**: Waitress (Production-ready WSGI server).
*   **AI Model**: Google **Gemini 2.0 Flash** (via `google-generativeai`).
*   **RAG & NLP**: `scikit-learn` (TF-IDF, Cosine Similarity), `numpy`.
*   **Data Source**: `youtube-transcript-api`.

---

## ⚙️ Installation & Setup

Follow these steps to run Vistify locally.

### Prerequisites
*   **Node.js** (v14+ recommended)
*   **Python** (v3.8+ recommended)
*   A **Google Gemini API Key** (Get one [here](https://aistudio.google.com/app/apikey))

### 1. Clone the Repository
```bash
git clone https://github.com/justishika/Video-Gist-Generator.git
cd Video-Gist-Generator
```

### 2. Backend Setup (Flask API)
Navigate to the API directory and set up the Python environment.

```bash
cd Flask-API

# Create a virtual environment
python -m venv .venv

# Activate the virtual environment
# On Windows:
.venv\Scripts\activate
# On macOS/Linux:
source .venv/bin/activate

# Install dependencies
pip install -r requirements.txt
```

**Configure API Key:**
Open `Flask-API/config.py` and replace the placeholder with your actual Gemini API key:
```python
GEMINI_API_KEY = 'YOUR_ACTUAL_API_KEY_HERE'
```

**Run the Server:**
```bash
# Starts the production server using Waitress
python start_server.py
```
The backend will run on `http://0.0.0.0:5000`.

### 3. Frontend Setup
Open a new terminal window, return to the project root, and install frontend dependencies.

```bash
# Return to root directory if you are in Flask-API
cd .. 

# Install dependencies
npm install

# Start the development server
npm start
```
The application will open in your browser at `http://localhost:1234`.

---

## 📖 Usage Guide

1.  **Paste URL**: Copy a YouTube video URL and paste it into the search bar.
2.  **Summarize**:
    *   Click **"Summarize in 10 Points"** for a quick overview.
    *   Click **"In-Depth Summary"** for a detailed report.
3.  **Explore**:
    *   Use **"Extract Entities & Facts"** to see structured data.
    *   Click **"Ask Questions"** to open the chat interface.
    *   Use **"Get Insights"** for suggested questions.
4.  **Analyze**: Check the metrics bar at the bottom of every chat response to verify accuracy.

---

## 📄 License
This project is licensed under the MIT License.
