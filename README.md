# 🤖 AI Email Reply Generator (Monorepo)

A mono-repository project that provides an AI-powered email reply generation service. It leverages the Gemini API via a Spring Boot backend and offers two primary ways to interact with the service: a React-based web interface and a Chrome Extension for direct use within Gmail.

## ✨ Core Features

* **AI-Powered Reply Generation**: Utilizes the Gemini API to generate intelligent and contextually relevant email replies.
* **Tone Control**: Allows the user to specify a tone (e.g., "professional," "casual," or "friendly") to influence the generated response.
* **Web Demo Interface**: A simple React frontend for demonstrating the API functionality.
* **Gmail Integration**: A Chrome Extension that injects an "AI Reply" button directly into the Gmail compose toolbar.

## 📂 Project Structure

This is a mono-repository containing three main sub-projects:

└── ai-email-reply-generator-monorepo/
<br>&emsp;├── email-generate-backend/   Spring Boot API
<br>&emsp;├── email-writer-frontend/    React Web Demo
<br>&emsp;└── email-generate-extension/   Chrome/Gmail Content Script Extension

## 💻 Technologies Used

### Backend (`email-generate-backend`)

* **Framework**: Spring Boot 3.5.6
* **Language**: Java 21
* **AI Integration**: WebFlux (`WebClient`) for asynchronous calls to the Gemini API.
* **Build Tool**: Maven

### Frontend (`email-writer-frontend`)

* **Framework**: React (version 19.1.1)
* **Tooling**: Vite
* **Styling**: Material UI (`@mui/material`)
* **HTTP Client**: Axios

### Extension (`email-generate-extension`)

* **Platform**: Chrome (Manifest V3)
* **Language**: JavaScript

## 🚀 Getting Started

### 1. Backend Setup

1.  **Environment Variable**: Create a `.env` file or set an environment variable named `GEMINI_API_KEY` with your actual API key. The application reads this key.
2.  **Navigate**: `cd email-generate-backend`
3.  **Run**: Execute the Spring Boot application.
    ```bash
    ./mvnw spring-boot:run
    # The API will be available on http://localhost:8080
    ```

### 2. Frontend Web Demo Setup

1.  **Navigate**: `cd email-writer-frontend`
2.  **Install Dependencies**:
    ```bash
    npm install
    ```
3.  **Run**:
    ```bash
    npm run dev
    # This typically starts the web demo on http://localhost:5173
    ```

### 3. Chrome Extension Setup

1.  **Navigate**: Go to the `email-generate-extension` directory.
2.  **Open Chrome Extensions**: Go to `chrome://extensions/` in your Chrome browser.
3.  **Enable Developer Mode**: Toggle "Developer mode" on (usually in the top right corner).
4.  **Load Unpacked**: Click the "Load unpacked" button.
5.  **Select Directory**: Select the `email-generate-extension` directory.
6.  **Usage**: The extension is now active and will inject the "AI Reply" button into the Gmail compose window.

---

---

## 📌 API Endpoint

The backend provides a single, simple REST endpoint for email generation.

| Method | Endpoint             | Consumes          | Produces   | Description                                                   |
|--------|----------------------|------------------|------------|---------------------------------------------------------------|
| POST   | `/api/email/generate` | `application/json` | `text/plain` | Generates a reply for the given email content and optional tone. |

**Request Body (`EmailRequestDto`):**

```json
{
  "emailContent": "The original email text goes here.",
  "tone": "professional" // Optional: "casual", "friendly", "professional", etc.
}
```


## 🤝 Contributing

Contributions are what make the open-source community such an amazing place to learn, inspire, and create. Any contributions you make are **greatly appreciated**.

If you have a suggestion that would make this better, please fork the repo and create a pull request. You can also simply open an issue with the tag "enhancement".
Don't forget to give the project a star! Thanks!
