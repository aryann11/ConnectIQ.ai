

```markdown
# 📨 Cold Email Generator  

A highly specialized Flask-based web application that seamlessly integrates advanced Generative AI, persistent vector databases, and automated workflows to generate hyper-personalized cold emails for business development. This tool is engineered for efficiency and precision, designed to identify job opportunities, query relevant portfolio projects, and draft compelling emails for client outreach.

---

## 🚀 Core Features  

### 🕵️‍♂️ Job Post Extraction  
- Scrapes structured job postings directly from career pages using a custom web scraper powered by `langchain_community.document_loaders`.  
- Processes unstructured HTML content into actionable job details, including `company`, `role`, `experience`, `skills`, and `description`.  

### 📊 Portfolio Recommendation System  
- Utilizes **ChromaDB** as a persistent vector database for efficient skill-based portfolio matching.  
- Dynamically queries portfolio projects based on job requirements using cosine similarity on embedded vectors.  

### 🤖 Cold Email Generation  
- Employs **Groq LLM (Llama-3.1-70b-versatile)** for natural language generation.  
- Tailors email drafts based on job descriptions, extracted skills, and portfolio data to maximize client engagement.  
- Uses prompt engineering via **LangChain** for precise and structured email generation.  

### 🧩 Modular Architecture  
- Cleanly decouples scraping, database management, and AI tasks for maintainability and scalability.  
- Ensures that each module is independently testable, making it easier to extend functionality.

---

## 🛠️ Technology Stack  

| **Component**              | **Technology**                                | **Description**                                   |
|----------------------------|-----------------------------------------------|-------------------------------------------------|
| **Backend Framework**      | Flask                                         | Web server and API handling                     |
| **Generative AI**          | Groq (Llama-3.1-70b-versatile)                | Generates cold emails using natural language    |
| **Database**               | ChromaDB                                      | Persistent vector storage for portfolio matching |
| **Web Scraping**           | LangChain WebBaseLoader                       | Extracts text content from career pages         |
| **Data Processing**        | Pandas                                        | Cleans and structures job data                 |
| **Output Parsing**         | LangChain JsonOutputParser                    | Ensures responses adhere to valid JSON format  |
| **Frontend**               | HTML & Jinja2                                | Minimalistic web interface                     |

---

## 📂 Project Structure  

```plaintext
|-- app.py                  # Main Flask application file
|-- templates/              # Frontend templates (HTML files)
|   |-- index.html          # User interface for input submission
|-- vectorstore/            # Persistent ChromaDB storage
|-- my_portfolio.csv        # CSV containing Techstack and Links
|-- requirements.txt        # Dependencies required for the project
|-- README.md               # Documentation (this file)
```

---

## ⚙️ Setup and Installation  

Follow these steps to get started with the Cold Email Generator:

### 1. Clone the Repository  
```bash
git clone https://github.com/<your-username>/<your-repo>.git
cd <your-repo>
```

### 2. Install Dependencies  
Install the required Python packages:  
```bash
pip install -r requirements.txt
```

### 3. Configure Environment Variables  
Set up the following environment variables in your system:  
- **`GROQ_API_KEY`**: Your API key for the Groq model.  
- **`USER_AGENT`**: User-agent string for web scraping (default provided).  

### 4. Add Portfolio Data  
Place a CSV file named `my_portfolio.csv` in the root directory. The file must contain:  
- **`Techstack`**: Skills or technologies associated with the project.  
- **`Links`**: URLs to the project details or demos.

### 5. Run the Application  
Start the Flask development server:  
```bash
python app.py
```


---

## 🔄 Workflow Overview  

1. **User Input**: Submit a career page link through the web interface.  
2. **Web Scraping**: Extract job postings and convert them into structured JSON format.  
3. **Portfolio Query**: Match the extracted skills with relevant portfolio items using vector embeddings.  
4. **Cold Email Drafting**: Generate a personalized email using AI, tailored to the job and portfolio context.  
5. **Output**: Receive a professional cold email in JSON format, ready to use.

---

## 📤 Sample Input & Output  

### Input  
**Career Page URL**:  
```plaintext
https://example.com/careers
```

### Output (Generated Cold Email)  
```json
{
  "content": "Dear [Hiring Manager at Company],\n\nI am Mohan, Business Development Executive at AtliQ..."
}
```

---

## 📊 Key Challenges Addressed  

1. **Parsing Unstructured Data**: Efficiently converts complex website content into structured job postings.  
2. **Portfolio Mapping**: Dynamic skill-based recommendation engine powered by ChromaDB.  
3. **Email Personalization**: Context-aware language generation using Groq’s state-of-the-art LLM.  
4. **Scalability**: Modular codebase ensures ease of extension and integration with additional services.

---

## 🤝 Contribution  

Contributions are welcome! If you want to enhance the project or report bugs:  
1. Fork the repository.  
2. Create a new feature branch:  
   ```bash
   git checkout -b feature/your-feature
   ```  
3. Submit a pull request.

---

