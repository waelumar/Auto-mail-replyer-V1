# Auto-mail-replyer-V1
This project automates email responses using a Large Language Model (LLM). The system extracts emails, analyzes their content, and generates contextually relevant replies using generative AI


Setting Up Credentials for Gmail API and Gemini API in the Code

To use this automated email responder, you need to set up authentication credentials for both **Google Gmail API** and Gemini API. Here’s how you can configure them:  

 1. Setting Up Gmail API Credentials**  

To authenticate and access your Gmail account programmatically, follow these steps:  

1. Enable the Gmail API:  
   - Go to the [Google Cloud Console](https://console.cloud.google.com/).  
   - Create a new project (or use an existing one).  
   - Navigate to APIs & Services → Library.  
   - Search for "Gmail API" and enable it.  

2. Create OAuth 2.0 Credentials:  
   - Go to **APIs & Services** → **Credentials**.  
   - Click **Create Credentials** → **OAuth client ID**.  
   - Choose **Desktop App** as the application type.  
   - Download the generated `credentials.json` file.  

3. Store Credentials and Token File:  
   - Save the `credentials.json` file in the same directory as your script.  
   - Set the `CREDENTIALS_FILE` variable in the script:  
     ```python
     CREDENTIALS_FILE = "credentials.json"
     ```
   - The first time you run the script, it will ask for authentication. This will generate a `token.json` file, which should be referenced in your script:  
     ```python
     TOKEN_FILE = "token.json"
      



#### 2. Setting Up Google Gemini API

To use the Google Gemini API for generating email responses:  

1. Obtain Your API Key:  
   - Go to the [Google AI Studio](https://aistudio.google.com/).  
   - Sign in with your Google account.  
   - Generate a new API key under **API Keys**.  
   - Copy the API key and store it securely.  

2. Link the API Key in the Code:  
   - Paste your Gemini API key in the script:  
     ```python
     GEMINI_API_KEY = "your_gemini_api_key_here"
     ```  
   - The code will use this key to communicate with the Gemini model and generate responses.


### How the Code Works  

This script is a **prototype (Version 1) for an AI-driven email automation system. It integrates Google's Gmail API to read emails and Google Gemini API to generate AI-driven responses. The workflow is as follows:  

1. Authenticate Gmail API:  
   - The script authenticates the Gmail API using OAuth 2.0.  
   - If the user has not authenticated before, it prompts them to log in and stores a token (`token.json`) for future use.  

2. Fetch the Latest Email:  
   - The script retrieves the most recent email from the inbox.  
   - It extracts the sender's email, subject, and message body.  

3. Generate an AI-Powered Response:  
   - The extracted email content is sent to **Google Gemini API**.  
   - The AI generates a natural, human-like reply based on the email’s context.  

4. User Confirmation & Sending Response:  
   - The AI-generated response is displayed for user review.  
   - The user can approve or modify it before sending.  
   - If approved, the response is sent back to the original sender.  

5. Optional Attachments:  
   - The user can attach a file before sending the email.  

6. Sending New Emails:  
   - The script allows the user to compose and send new emails manually, including optional attachments.  


### Future Plans - Developing a Custom LLM Model

This is just **Version 1** of the AI-powered email automation system. Currently, it relies on **Google's Gemini API** for generating responses. However, the long-term goal is to develop a **custom LLM (Large Language Model)** that produces more accurate and contextually aware responses. The future improvements aim to:  

Improve response personalization and adaptability.  
Reduce dependency on third-party APIs for better efficiency.  
Offer more refined and context-sensitive email replies.  

This prototype serves as a foundational step toward building a more advanced, self-hosted LLM** for email automation and AI-driven communication. 🚀

NOTE:
The code recieves email only from the gmail account which is permitted to acess when the api key is extracted from google cloud




