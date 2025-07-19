# 🌾 KrishiSakhi: AI-Driven Farming Assistant

## Overview
KrishiSakhi is an advanced, multilingual, AI-powered assistant for farmers and agricultural professionals. It combines conversational AI, crop and disease analytics, market tools, and community features in a single Streamlit web application.

## 🚀 Features
1. **AgriBot Chat (Home Page)**
   - Conversational AI assistant powered by Google Gemini (Gemini 2.0).
   - Supports text and image input for plant disease diagnosis and general queries.
   - Multilingual UI (English, Hindi, Telugu, Tamil, Kannada, Malayalam).
   - Chat history per user session.
   - Minimal, user-friendly chat interface.
2. **Crop & Soil Recommendations**
   - Input farm data (N, P, K, pH, moisture, temperature, rainfall, crop type, etc.).
   - Data-driven crop recommendation using Crop_recommendation.csv.
   - Fertilizer advice using fertilizer.csv.
   - Market trends, weather forecast, and sustainability tips.
3. **AI Disease Diagnosis**
   - Upload plant images or describe symptoms (text/voice).
   - AI model predicts disease, confidence, and suggests treatment.
   - Severity estimation and farmer feedback/correction workflow.
4. **Growth Diary**
   - Log daily crop growth, notes, images, and weather.
   - View and manage diary entries.
5. **Knowledge Sharing Forum**
   - Community Q&A and discussion threads.
   - Post and reply (text/audio) to threads.
6. **Soil Health Scanning**
   - Log and view soil test results (pH, N, P, K, organic matter, notes).
7. **Live Agri Heatmaps**
   - Visualize simulated disease outbreaks on a map.
   - Suggest suitable crops for user’s region.
8. **Khet Market**
   - Buy/sell crops and equipment directly (no middlemen).
   - User registration, login, cart, checkout, and payment simulation.
   - List crops for sale with images and MSP validation.
   - View orders and manage listings.
9. **Analytics Dashboard**
   - Visualize AgriBot chat usage, crop/disease trends, user engagement, and question types.
   - Upload and auto-visualize custom CSV datasets.
10. **Multilingual Support**
    - All UI and navigation available in 6 Indian languages.
    - Language can be changed instantly from the sidebar.
11. **User/Admin Login & Role-Based Access**
    - Login system at app start: Admin (`surya001`/`1234`) and normal users (any other credentials).
    - Admin can access the "Get Corpus Data" page to download all user input logs as a CSV file.
    - Normal users have access to all features except corpus data download.
12. **Comprehensive User Input Logging**
    - All user actions are logged with timestamp and username in `user_input_log.csv`.
    - Data can be exported for research and analytics (admin only).
13. **Audio Recording Support**
    - Audio recording for disease diagnosis and forum replies is supported via `streamlit-audiorecorder`.
    - If you see a message about missing `streamlit-audiorecorder`, install it with:
      ```sh
      pip install streamlit-audiorecorder
      ```

## 📂 Datasets Used
- **Crop_recommendation.csv:** For crop prediction based on soil and weather parameters.
- **fertilizer.csv:** For fertilizer recommendations by crop.
- **archive/train/** and **archive/test/**: Plant disease image datasets, organized by crop/disease class.
- **KHETGPT/dataset_farming/**: Stores logs for growth diary, forum threads, and soil tests.
- **vosk-model-small-en-us-0.15/**: Offline speech recognition model for voice input (optional).

## 🛠️ Installation & Setup
1. **Clone the repository:**
   ```sh
   git clone <repo-url>
   cd KHETGPT-main
   ```
2. **Install dependencies:**
   ```sh
   pip install -r requirements.txt
   ```
   - Required: streamlit, google-generativeai, werkzeug, pillow, python-dotenv, matplotlib, folium, streamlit-folium, vosk (optional for voice), streamlit-webrtc (optional for voice), streamlit-audiorecorder (optional for forum audio).
3. **Set up Gemini API key:**
   - Create a `.env` file in the root directory:
     ```
     GEMINI_API_KEY=your_google_gemini_api_key
     ```
   - Or set the key in your environment variables.
4. **(Optional) Download Vosk model for voice input:**
   - Place the `vosk-model-small-en-us-0.15` folder in the project root.

## ▶️ Running the App
```sh
streamlit run streamlit_app.py
```
The app will be available at http://localhost:8501 (or another port if specified).

## 📝 Notes
- All user data (chat, diary, forum, soil tests) is stored in local CSV/JSON files for demo purposes.
- For production, consider using a database (e.g., SQLite, PostgreSQL).
- The app is designed for educational and research use; not for medical or financial advice.

## 🙏 Credits
- **Developers:** [SURYA SAROJ SISTLA ]
- **Datasets:**
  - Crop Recommendation Dataset
  - PlantVillage Dataset
  - [Fertilizer Dataset] (source: included in repo)
- **AI Models:** Google Gemini, Vosk, custom image/NLP models
- **Libraries:** Streamlit, Google Generative AI, Folium, Matplotlib, Vosk, etc.

## 📧 Contact
For questions, suggestions, or contributions, please open an issue or contact sistlasree24@gmail.com

---

### Troubleshooting
- **TypeError: Object of type date/datetime is not JSON serializable:**
  - All date/datetime fields are now converted to ISO strings before logging. If you see this error, update your code as shown in the latest version.
- **NameError: name 'log_user_input' is not defined:**
  - Ensure the `log_user_input` function is defined at the top of `streamlit_app.py` after all imports.

--- 
