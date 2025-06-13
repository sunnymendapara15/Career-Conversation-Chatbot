---
title: Career-Conversation-Chatbot
app_file: app.py
sdk: gradio
sdk_version: 5.33.2
---
# Career-Conversation-Chatbot
The Career Conversation Chatbot answers career-related questions using a resume and summary, with tools to record user interest and unanswered queries via Pushover. It offers a professional Gradio interface.

## Features
- **Personalized Responses**: Answers questions about Sunny Mendapara’s career, skills, and experience based on `Sunny_Mendapara_Resume.pdf` and `summary.txt`.
- **Tool Integration**: Records user interest (email) and unknown questions via Pushover notifications.
- **Gradio Interface**: User-friendly chat UI accessible locally or via Hugging Face Spaces.
- **Minimal Design**: Focused functionality for portfolio websites.

## Prerequisites
- **Python 3.8+**
- **Conda environment** (recommended)
- **Dependencies** (listed in `requirements.txt`):
  ```plaintext
  langchain-groq
  python-dotenv
  gradio
  pypdf
  requests
  groq
  ```
- **Files**:
  - `Sunny_Mendapara_Resume.pdf`: Resume in PDF format.
  - `summary.txt`: Text summary of background.
  - `.env`: Environment variables (see below).
- **API Keys**:
  - **Groq API Key**: Obtain from [Grok Console](https://console.grok.ai).
  - **Pushover User Key and App Token**: Obtain from [Pushover](https://pushover.net).
  - **Hugging Face Token**: For Spaces deployment, from [Hugging Face Settings](https://huggingface.co/settings/tokens).

## Setup
1. **Clone the Repository**:
   ```bash
   git clone https://github.com/sunnymendapara15/Career-Conversation-Chatbot.git
   cd Career-Conversation-Chatbot
   ```

2. **Create Conda Environment**:
   ```bash
   conda create -n ai python=3.8
   conda activate ai
   ```

3. **Install Dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

4. **Configure Environment Variables**:
   - Create a `.env` file in the project root:
     ```plaintext
     GROQ_API_KEY=your_groq_api_key_here
     PUSHOVER_USER=your_pushover_user_key_here
     PUSHOVER_TOKEN=your_pushover_app_token_here
     HF_TOKEN=your_huggingface_token_here
     ```

5. **Ensure Files**:
   - Place `Sunny_Mendapara_Resume.pdf` and `summary.txt` in the project root.

## Usage
1. **Run Locally**:
   ```bash
   python app.py
   ```
   - Open `http://localhost:7860` in a browser to access the Gradio interface.
   - Test queries:
     - “What’s your experience?” → Answers based on resume/summary.
     - “My email is test@example.com” → Records email via Pushover.
     - “What’s the capital of Mars?” → Records unknown question via Pushover.

2. **Pushover Notifications**:
   - Receive notifications for recorded emails or unknown questions in the Pushover app.

## Deployment to Hugging Face Spaces
1. **Prepare Files**:
   - Ensure `app.py`, `requirements.txt`, `Sunny_Mendapara_Resume.pdf`, `summary.txt`, and `.env` are in the project root.
   - Verify `requirements.txt`:
     ```plaintext
     langchain-groq
     python-dotenv
     gradio
     pypdf
     requests
     groq
     ```

2. **Deploy**:
   ```bash
   gradio deploy
   ```
   - Enter your Hugging Face token or ensure `HF_TOKEN` is in `.env`.
   - If prompted, log in with `gradio login`.

3. **Upload Files to Space**:
   - If `Sunny_Mendapara_Resume.pdf` or `summary.txt` are missing, upload them via the Space’s web interface: `https://huggingface.co/spaces/your-username/your-space-name` > **Files** > **Upload Files**.

4. **Access**:
   - Use the Space URL (e.g., `https://your-username-your-space-name.hf.space`) to interact with the chatbot.

## License
MIT License. See [LICENSE](LICENSE) for details.

## Contact
For issues or contributions, open an issue on the [GitHub repository](https://github.com/sunnymendapara15/Career-Conversation-Chatbot).
