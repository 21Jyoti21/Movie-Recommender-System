# 🎬 Movie Recommender System

A content-based movie recommendation system that suggests similar movies based on user selection. Built with Python, Machine Learning, and deployed using Streamlit.

## 🚀 Live Demo

**Try it now:** [Movie Recommender System](https://movie-recommender-system-tvgczxn9icynk7p6w6khez.streamlit.app/)

## 📋 Overview

This project implements a content-based filtering recommendation system that analyzes movie metadata (genres, keywords, cast, crew, and overview) to suggest similar movies. The system uses natural language processing and cosine similarity to find movies with similar characteristics.

## ✨ Features

- **Content-Based Filtering**: Recommends movies based on content similarity
- **Interactive UI**: User-friendly interface built with Streamlit
- **Movie Posters**: Fetches movie posters using TMDb API
- **Real-time Recommendations**: Instant suggestions upon movie selection
- **5000+ Movies Database**: Trained on TMDb 5000 movies dataset

## 🛠️ Technologies Used

- **Python 3.x**
- **Streamlit** - Web application framework
- **Pandas & NumPy** - Data manipulation and analysis
- **Scikit-learn** - Machine learning (CountVectorizer, Cosine Similarity)
- **NLTK** - Natural language processing (Porter Stemmer)
- **Pickle** - Model serialization
- **TMDb API** - Movie posters and metadata

## 📊 Dataset

The project uses the [TMDb 5000 Movie Dataset](https://www.kaggle.com/datasets/tmdb/tmdb-movie-metadata) which contains:
- `tmdb_5000_movies.csv` - Movie metadata (genres, keywords, overview, etc.)
- `tmdb_5000_credits.csv` - Cast and crew information

## 🔧 Installation & Setup

### Prerequisites
- Python 3.7 or higher
- pip package manager

### Local Installation

1. **Clone the repository**
```bash
git clone https://github.com/21Jyoti21/Movie-Recommender-System.git
cd Movie-Recommender-System
```

2. **Install dependencies**
```bash
pip install -r requirements.txt
```

3. **Run the application**
```bash
streamlit run app.py
```

4. **Access the app**
Open your browser and go to `http://localhost:8501`

## 📁 Project Structure

```
Movie-Recommender-System/
│
├── data/
│   ├── tmdb_5000_movies.csv      # Movies dataset
│   └── tmdb_5000_credits.csv     # Credits dataset
│
├── app.py                         # Streamlit web application
├── MovieRecommendationSys.ipynb   # Jupyter notebook (data preprocessing & model)
├── movies.pkl                     # Processed movie data
├── movie_dict.pkl                 # Movie dictionary
├── similarity.pkl                 # Similarity matrix (176 MB - Git LFS)
├── requirements.txt               # Python dependencies
├── Procfile                       # Deployment configuration
├── setup.sh                       # Setup script
└── README.md                      # Project documentation
```

## 🧠 How It Works

1. **Data Preprocessing**
   - Merges movie and credits datasets
   - Extracts relevant features (genres, keywords, cast, crew, overview)
   - Converts JSON-like strings to Python lists

2. **Feature Engineering**
   - Creates a `tags` column combining all features
   - Applies stemming using Porter Stemmer
   - Removes spaces from multi-word entries

3. **Vectorization**
   - Uses CountVectorizer with 5000 max features
   - Converts text data into numerical vectors
   - Removes English stop words

4. **Similarity Calculation**
   - Computes cosine similarity between movie vectors
   - Creates a 4803×4803 similarity matrix

5. **Recommendation**
   - Finds movies with highest similarity scores
   - Returns top 5 similar movies with posters

## 📸 Screenshots

![Movie Recommender System Demo](https://via.placeholder.com/800x400?text=Add+Your+Screenshot+Here)

## 🔑 API Key Setup

To fetch movie posters, you need a TMDb API key:

1. Create an account at [TMDb](https://www.themoviedb.org/)
2. Get your API key from account settings
3. Replace the API key in `app.py`:
```python
response = requests.get('https://api.themoviedb.org/3/movie/{}?api_key=YOUR_API_KEY&language=en-US'.format(movie_id))
```

## 📦 Dependencies

```
streamlit
pandas
numpy
scikit-learn
nltk
requests
pickle-mixin
```

## 🚀 Deployment

This application is deployed on **Streamlit Community Cloud**. To deploy your own version:

1. Push your code to GitHub
2. Sign in to [Streamlit Cloud](https://share.streamlit.io/)
3. Connect your GitHub repository
4. Deploy with `app.py` as the main file

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📝 Future Enhancements

- [ ] Add user ratings-based collaborative filtering
- [ ] Implement hybrid recommendation system
- [ ] Add movie search functionality
- [ ] Include more movie metadata (release year, ratings, etc.)
- [ ] Add pagination for recommendations
- [ ] Implement caching for faster performance

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

## 👨‍💻 Author

**Jyoti**
- GitHub: [@21Jyoti21](https://github.com/21Jyoti21)
- Project Link: [Movie Recommender System](https://github.com/21Jyoti21/Movie-Recommender-System)

## 🙏 Acknowledgments

- [TMDb](https://www.themoviedb.org/) for providing the movie database API
- [Kaggle](https://www.kaggle.com/) for the dataset
- [Streamlit](https://streamlit.io/) for the amazing web framework

---

⭐ If you found this project helpful, please give it a star!
