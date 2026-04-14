# 🎬 Cine Recommendation System

Content-based movie recommender using TF-IDF on 45k+ movies (tags: overview+genres+tagline) + TMDB for posters/details/genre recs.

## Features
- **FastAPI Backend** (`main.py`): TF-IDF similarity, TMDB integration, /health, /home, /search, /recommend.
- **Streamlit Frontend** (`app.py`): Home feed, search+recs grids with posters, TF-IDF direct.
- Responsive cards, caching, error handling.

## Setup
1. Install deps (wheels):
   ```
   pip install -r requirements.txt
   ```
   **Pip build fail?** Use conda:
   ```
   conda create -n cine python=3.11 -y
   conda activate cine
   conda install pandas numpy scikit-learn -y
   pip install -r requirements.txt
   ```

2. **Optional** TMDB API key: Edit `.env` (free at themoviedb.org). Without it, local TF-IDF recs work, TMDB features fallback.

3. **Run Backend** (terminal 1):
   ```
   python -m uvicorn main:app --reload
   ```
   API docs: http://localhost:8000/docs

4. **Run Frontend** (terminal 2):
   ```
   streamlit run app.py
   ```
   Open http://localhost:8501

## Data
- `preprocescode.ipynb`: Run to regenerate pickles from `movies_metadata.csv`.
- Dataset: 45k movies, TF-IDF (50k features).

## Usage
- **Home**: Popular/top movies grids.
- **Search**: Query -> TMDB matches -> TF-IDF sim + genre recs w/ posters.
- **TF-IDF**: Direct title-based recs.

## API Endpoints
See http://localhost:8000/docs

Enjoy! 🎥
