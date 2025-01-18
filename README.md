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
