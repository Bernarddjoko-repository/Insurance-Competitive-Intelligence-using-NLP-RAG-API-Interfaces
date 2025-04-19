![istockphoto-2194844746-612x612](https://github.com/user-attachments/assets/c05aeb88-c2f2-4de5-a430-b57e16b57da6)


# 📌 Insurance Competitive Intelligence AI<br>

## 🧠 Introduction<br>
Insurance companies frequently make strategic decisions based on their competitors' actions.<br>
This project leverages AI-powered document retrieval and NLP to analyze insurance financial reports.<br>
The goal is to provide competitive insights to support data-driven decisions in underwriting, strategy, and investment.<br>

## 📂 Dataset Overview<br>
We used publicly available 10-K financial reports from:<br>
- Allstate (ALL)<br>
- Travelers (TRV)<br>
- Chubb (CB)<br>
- Progressive (PGR)<br>

Reports were sourced from the SEC EDGAR database.<br>
Each document was chunked and embedded using SentenceTransformer and indexed via FAISS.<br>

## 🧩 Business Problem<br>
Insurers need visibility into how their peers manage risk, execute strategy, and respond to market trends.<br>
Manually analyzing lengthy 10-K filings is time-consuming and often inefficient.<br>
This tool enables AI-assisted Q&A to extract intelligence directly from these filings.<br>

## 🧭 Step-by-Step Approach<br>

### ✅ Step 1: Preprocessing<br>
- Chunked each 10-K report into manageable text segments<br>
- Generated vector embeddings using `all-MiniLM-L6-v2`<br>

### ✅ Step 2: FAISS Index Creation<br>
- Indexed embeddings in FAISS for fast semantic search<br>
- Stored metadata (company, section, chunk)<br>

### ✅ Step 3: Query Engine with Cohere<br>
- User enters question via Streamlit UI<br>
- FAISS retrieves top-matching chunks<br>
- Cohere API generates contextualized answers<br>

### ✅ Step 4: Frontend with Streamlit<br>
- Clean UI for user input and viewing results<br>
- Option to expand context and download answers<br>

## 🛠️ Challenges & Solutions<br>

### 🔹 Challenge 1: Large Document Parsing<br>
**Problem:** SEC files are hundreds of pages long<br>
**Solution:** Document chunking and memory-efficient processing pipeline<br>

### 🔹 Challenge 2: Context Relevance<br>
**Problem:** Poor matching for certain query types<br>
**Solution:** Tuned chunk size and FAISS parameters<br>

### 🔹 Challenge 3: API Environment Issues in Streamlit<br>
**Problem:** API keys not detected in some environments<br>
**Solution:** Used `.streamlit/config.toml` and `.env` loading fallback<br>

### 🔹 Challenge 4: Concise Answers<br>
**Problem:** Cohere initially returned short responses<br>
**Solution:** Increased prompt context and token length limit<br>

## 📊 Results<br>
- Deployed fully working prototype on Streamlit<br>
- Answered questions like "Compare Allstate’s and Traveler’s 2024 strategies"<br>
- Reduced research effort for competitive analysts<br>

## 🔭 Future Work<br>
- Multi-document comparison view<br>
- Add filters (year, section, carrier)<br>
- Expand to include quarterly (10-Q) and earnings call data<br>

## 🛠️ Installation & How to Run<br>

```bash
git clone https://github.com/your-username/insurance-competitive-intelligence-ai.git<br>
cd insurance-competitive-intelligence-ai<br>
python -m venv env && source env/bin/activate  # or .\env\Scripts\activate on Windows<br>
pip install -r requirements.txt<br>


### Key Takeaways
✔️ AI-powered competitive intelligence saves manual research time<txt>.
✔️ FAISS-based document retrieval improves query relevance<txt>.
✔️ Cohere AI provides context-aware responses<txt>.
✔️ Streamlit UI offers a simple, interactive experience<txt>.
✔️ The system can be expanded to other financial sectors<txt>.
