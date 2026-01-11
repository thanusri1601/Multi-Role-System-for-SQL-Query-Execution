# Multi Role System for SQL Query Execution

This project implements a Corrective Retrieval-Augmented Generation (CRAG) architecture to improve the factual reliability of large language model (LLM) responses. The system ingests content from a curated set of technical websites focused on agentic systems, prompt engineering, and advanced LLM concepts. Web data is programmatically scraped using BeautifulSoup, preprocessed, and segmented using configurable chunking strategies before being embedded and stored in a vector database.

During inference, relevant document chunks are retrieved based on semantic similarity and supplied as context to the LLM. The generated response is then evaluated for grounding and relevance. If the required context is successfully found within the indexed documents, the workflow terminates at the final response node.

If the context is not sufficiently supported by the retrieved documents, the system transitions to a query transformation node, where the original user query is refined and expanded. The transformed query is subsequently routed to a web search and retrieval pipeline, enabling the system to gather external information. The newly retrieved context is then reintroduced into the generation process to produce a corrected and better-grounded response.

Configuration details regarding the chunking strategy, embedding models, and vector database selection are maintained within the codebase.

## Workflow Graph

<p align="center">
  <img src="assets/image33.png" width="550">
</p>

---

## AWS Deployment Screenshot
<p align="center">
   
  <img src="assets/image4.jpeg" width="800">
</p>

 
<p align="center">
  
  ## Project Report

📥 *[Click here to view the Project Report (PDF)](assets/Report(3).pdf)**

</p>

---

## Setup

### 1. Clone the Repository
git clone (https://github.com/thanusri1601/Corrective-RAG-System-for-Knowledge-Retrieval.git)  
cd CRAG-System

---

### 2. Create Virtual Environment
python3 -m venv venv  
source venv/bin/activate  


---

### 3. Install Dependencies
pip install --upgrade pip  
pip install -r requirements.txt  

---

## Running the Application

### Local Execution
streamlit run app.py  

---

## AWS EC2 Deployment

This project is deployed on an AWS EC2 Ubuntu instance.

### Deployment Steps
1. Launch an Ubuntu EC2 instance  
2. Open port 8501 in the EC2 security group  
3. Clone this repository on the EC2 instance  
4. Create and activate a Python virtual environment  
5. Install required dependencies  
6. Run the Streamlit application  

Run the application on EC2 using:
streamlit run app.py --server.port 8501 --server.address 0.0.0.0  

## Live Deployment
http://ec2-3-91-215-180.compute-1.amazonaws.com:8501/

## Output

- Interactive Streamlit-based user interface  
- Corrective Retrieval-Augmented Generation workflow  
- Reduced hallucinations through validation and corrective retrieval  
- Publicly accessible AWS EC2 deployment  

---

## Technologies Used

- Python  
- LangChain  
- LangGraph  
- FAISS Vector Store  
- OpenAI API  
- Streamlit  
- AWS EC2  

---

## Key Contributions

- Implemented Corrective Retrieval-Augmented Generation (CRAG) to improve factual grounding  
- Designed an agent-based workflow using LangGraph  
- Introduced validation and corrective retrieval to mitigate hallucinations  
- Deployed an end-to-end LLM system on AWS EC2  

---

## Author

Thanusri A  
