Project Overview:

This Python project automates the processing of PDFs from URLs, generating summaries, extracting keywords, and storing results in a MongoDB database. It leverages powerful libraries like requests for downloads,
PyPDF2 for text extraction from PDFs, transformers for text summarization (facebook/bart-large-cnn),sklearn for keyword extraction (TfidfVectorizer), and pymongo for interaction with MongoDB.

Prerequisites:

Python 3.x (https://www.python.org/downloads/)
Necessary libraries: requests, PyPDF2, transformers, sklearn, pymongo
MongoDB server (https://www.mongodb.com/try/download/community)
Jupyter Notebook (https://jupyter.org/)

Installation:

Install Python and create a virtual environment (recommended for managing project dependencies):
python3 -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate.bat

Install required libraries using following command:
pip install requests PyPDF2 transformers sklearn pymongo

Install Jupyter Notebook using command:
pip install jupyter notebook

Setting Up MongoDB

1.  Download and install MongoDB server according to your operating system (https://www.mongodb.com/try/download/community).   

Start the MongoDB server:
mongod --dbpath /path/to/data/dir  # Replace with your data directory path

Create a database (e.g., "summary") and a collection (e.g., "py") within MongoDB using a tool like mongo or a graphical client.

Connecting MongoDB in Jupyter Notebook

Python
from pymongo import MongoClient

# Replace with your MongoDB connection details
client = MongoClient("mongodb://localhost:27017/")
db = client["summary"]
collection = db["py"]

Code Structure

1. Dependencies:
Import necessary libraries.
                                                 
2. Summarization Pipeline:
Initialize the pre-trained facebook/bart-large-cnn model for summarization.
                                                 
3. MongoDB Configuration:
Create a connection to the MongoDB server, database, and collection.
                                                 
4. Download Function (download_pdf):
Downloads a PDF from the provided URL and saves it locally.
Handles errors and logs status codes.
                                                 
5. Text Extraction Function (extract_text_from_pdf):
Extracts plain text from a PDF file using PyPDF2.
Handles potential errors during extraction.
                                                 
6. Summary Generation Function (generate_summary):
Uses the summarizer pipeline to generate a concise summary of the extracted text.
Allows specifying summary length ('short', 'medium', or 'long' as strings).
Handles errors gracefully and returns an empty string if necessary.
                                                 
7. Keyword Extraction Function (extract_keywords):
Employs TfidfVectorizer to identify important keywords from the text.
Sets a limit on the number of keywords returned (adjustable if needed).
Deals with potential errors during processing.
                                                 
8. Process Single PDF Function (process_pdf_from_url):
Takes a PDF URL as input.
Derives the filename from the URL and creates a directory for downloaded PDFs.
Downloads the PDF using the download_pdf function.
Extracts text, generates summary, and extracts keywords if download is successful.
Stores metadata and extracted results in the MongoDB collection.
Prints progress messages for each step.
                                                 
9. Process Multiple PDFs Function (process_pdfs_from_urls):
Takes a list of PDF URLs as input.
Utilizes ProcessPoolExecutor for parallel processing (optional for efficiency).
Calls process_pdf_from_url for each URL in the list.
Prints messages for starting and finishing processing.
                                                      
10. Example Usage:
Provides a sample list of PDF URLs to demonstrate usage.
Running the Script

Open Jupyter Notebook and create a new Python 3 notebook.

Copy and paste the code into your notebook.

Replace the placeholder URL list (pdf_urls) with your desired PDF URLs.

Replace MongoDB connection details in the MongoClient if necessary.
