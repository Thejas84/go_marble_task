# go_marble_task

**Product Review Scraping and Summarizing API**


This project provides an API to scrape and summarize product reviews from different e-commerce platforms (like Amazon, Flipkart, etc.) using Playwright and OpenAI GPT. It extracts reviews, summarizes them, and provides a simple interface for users to fetch summarized reviews from any product page URL.

**Solution Approach**


**1. Overview**


FastAPI is used to create the API server.
Playwright is employed to scrape reviews from product pages (Amazon, Flipkart, or generic websites).
OpenAI's GPT-3.5 or GPT-4 is used to summarize the scraped reviews.
The ngrok service is used to expose the FastAPI app to the public internet for easy access.


**2. System Architecture**

![flowchart](https://github.com/user-attachments/assets/408ae9e8-a8e0-4cdf-85a2-a8a1ad2163e7)

**3. Key Components**


FastAPI:
A modern, fast (high-performance) web framework for building APIs with Python 3.7+ based on standard Python type hints.
Playwright:
A browser automation tool used to scrape reviews from various websites like Amazon and Flipkart.
OpenAI GPT-3/4:
OpenAI's language model used to summarize the reviews.
ngrok:
Exposes the local FastAPI app to the internet for testing and production use.


**4. Workflow**


The user sends a GET request to the /api/reviews endpoint, providing a product page URL as a query parameter.
The backend uses Playwright to scrape the reviews from the specified URL.
The scraped reviews are then passed to OpenAI GPT for summarization.
The summarized reviews, along with the raw reviews, are returned to the user in a structured JSON format.




**How to Run the Project**

**1. Install Prerequisites**

Clone the repository:
[git clone https://github.com/your-username/repository-name.git](https://github.com/Thejas84/go_marble_task.git)

cd repository-name

Create a virtual environment (optional but recommended):

python -m venv venv
venv\Scripts\activate  # On Windows
source venv/bin/activate  # On MacOS/Linux

Install dependencies:

pip install -r requirements.txt
This installs all the required libraries, including FastAPI, Playwright, OpenAI, etc.
Install Playwright Browsers: Playwright requires a browser to run in the background for scraping:

python -m playwright install
Set up your OpenAI API key:

Replace the openai.api_key in the code with your actual OpenAI API key.
Set up your ngrok token:

Replace the ngrok.set_auth_token with your actual ngrok token.



**2. Run the FastAPI App Locally**


To run the FastAPI application with ngrok, use the following command:

uvicorn app:app --reload
This will run the server on http://127.0.0.1:8000. Ngrok will provide a public URL that will look like https://<random-string>.ngrok.io.

3. Access the API
Once the app is running, you can test it by visiting the public ngrok URL provided in the terminal.

API Usage
GET /api/reviews
Fetches product reviews and provides a summary.

Query Parameters:
url: The product page URL (e.g., Amazon, Flipkart, etc.)


Example Request:

GET https://<your-ngrok-url>/api/reviews?url=https://www.amazon.com/dp/B08L5TNJHG


{

  "reviews_count": 50,

  "reviews": [
  
    {
    
      "title": "Great Product",
      
      "body": "I love this product. It works as expected.",
      
      "rating": 5,
      
      "reviewer": "John Doe"

    },
    
    {
      "title": "Not bad",
      
      "body": "The product is okay, but it could be improved.",
      
      "rating": 3,
      
      "reviewer": "Jane Smith"
      
    }

  ],

  "summarized_reviews": "The product has received mixed reviews. Some customers are happy with its performance, while others feel it could be improved. Overall, it has a rating of 3.5 out of 5."

  
}




 Responses:

![Screenshot (338)](https://github.com/user-attachments/assets/0b8dd752-290d-445c-9f7e-b3b80c5505b7)



**Troubleshooting**


Error 500: If the scraping fails, check the logs for errors related to Playwright or OpenAI. You may need to adjust the scraping selectors for specific websites.


ngrok Connection: Ensure that ngrok is running properly. If ngrok disconnects, restart the app and the ngrok tunnel.


