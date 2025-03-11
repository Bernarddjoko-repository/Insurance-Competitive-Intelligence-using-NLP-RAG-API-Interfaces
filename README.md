![istockphoto-2194844746-612x612](https://github.com/user-attachments/assets/c05aeb88-c2f2-4de5-a430-b57e16b57da6)


## 📌 Insurance Competitive Intelligence AI
### Introduction
Insurance companies frequently make strategic decisions based on their competitors' actions<txt>. This project leverages AI-powered document retrieval and natural language processing (NLP) to analyze insurance companies' financial reports<txt>. The goal is to provide competitive intelligence insights, helping insurers understand market trends, financial strategies, and risk factors of their competitors<txt>.

Our Insurance Competitive Intelligence AI allows users to input queries and retrieve AI-generated insights based on pre-processed 10-K financial statements of major insurance firms<txt>.

### Dataset Overview
The dataset consists of publicly available 10-K financial reports from major insurance companies such as:<txt>

Allstate (ALL)<txt>
Progressive (PGR)<txt>
Travelers (TRV)<txt>
Chubb (CB)<txt>
These reports are retrieved from the SEC EDGAR database and contain financial performance, risk factors, and business strategies<txt>.

The data is processed using FAISS (Facebook AI Similarity Search) for efficient retrieval and embedding-based document search<txt>.

### Business Problem
Insurance firms require competitive intelligence to:<txt>
✔️ Identify strategic initiatives of competitors<txt>
✔️ Compare financial performance across companies<txt>
✔️ Analyze market risks & trends<txt>

However, extracting meaningful insights from large, unstructured financial documents is challenging<txt>. Traditional methods rely on manual analysis, which is slow and inefficient<txt>. This project aims to automate competitive intelligence analysis using AI-powered document retrieval and NLP<txt>.

### Step-by-Step Approach
1️⃣ Data Processing & Embedding
Extract text from 10-K filings<txt>.
Segment reports into smaller chunks<txt>.
Generate sentence embeddings using SentenceTransformer<txt>.
2️⃣ Building FAISS Search Index
Convert text embeddings into a searchable FAISS index<txt>.
Store metadata (company name, section, chunk text)<txt>.
3️⃣ AI-Powered Query Answering
User enters a question about competitors<txt>.
FAISS retrieves relevant document chunks<txt>.
Chunks are passed to Cohere API for AI-generated responses<txt>.
4️⃣ Frontend Deployment
Streamlit provides an interactive UI<txt>.
Users can input queries and receive AI-generated financial insights<txt>.

### Challenges & Solutions
🔹 Challenge 1: Handling Large 10-K Reports
Problem: SEC filings are hundreds of pages long, making retrieval difficult<txt>.
Solution: We split documents into smaller chunks and indexed them using FAISS for efficient retrieval<txt>.

🔹 Challenge 2: Improving Query Relevance
Problem: Queries sometimes retrieved irrelevant document chunks<txt>.
Solution: We optimized embeddings and fine-tuned retrieval parameters in FAISS<txt>.

🔹 Challenge 3: Streamlit Not Recognizing Environment Variables
Problem: The API key wasn’t detected in Streamlit runtime<txt>.
Solution: We loaded environment variables via .streamlit/config.toml<txt>.

🔹 Challenge 4: Short AI Responses
Problem: AI-generated responses were too brief<txt>.
Solution: Increased context window and response length in Cohere API settings<txt>.

### Results
✅ Successfully built an interactive AI-powered system for analyzing insurance financials<txt>.
✅ Accurate retrieval of financial insights from 10-K filings<txt>.
✅ Streamlit-based UI for easy query input and AI responses<txt>.
✅ Competitive intelligence automation, reducing manual report analysis time<txt>.

### Future Work
🔹 Expand dataset to more insurance companies<txt>.
🔹 Fine-tune retrieval models for better query relevance<txt>.
🔹 Implement multi-document comparison for deeper competitor analysis<txt>.
🔹 Improve AI-generated summaries with more structured insights<txt>.

### Installation & How to Run
🔹 1. Clone the Repository
bash
Copy
Edit
git clone https://github.com/your-github-username/insurance-competitive-intelligence-ai.git
cd insurance-competitive-intelligence-ai
🔹 2. Create a Virtual Environment & Install Dependencies
bash
Copy
Edit
python -m venv env
source env/bin/activate  # For MacOS/Linux
env\Scripts\activate  # For Windows
pip install -r requirements.txt
🔹 3. Set Up API Keys
Create a .env file and add your Cohere API key:<txt>

ini
Copy
Edit
COHERE_API_KEY=your-api-key-here
For Streamlit, configure:<txt>

bash
Copy
Edit
mkdir ~/.streamlit
echo "[server]" > ~/.streamlit/config.toml
echo "COHERE_API_KEY='your-api-key-here'" >> ~/.streamlit/config.toml
🔹 4. Run the Application
bash
Copy
Edit
streamlit run App.py
Go to http://localhost:8501 in your browser and start querying financial insights<txt>!

### Key Takeaways
✔️ AI-powered competitive intelligence saves manual research time<txt>.
✔️ FAISS-based document retrieval improves query relevance<txt>.
✔️ Cohere AI provides context-aware responses<txt>.
✔️ Streamlit UI offers a simple, interactive experience<txt>.
✔️ The system can be expanded to other financial sectors<txt>.
