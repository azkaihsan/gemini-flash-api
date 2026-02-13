# Gemini Flash API

A simple Express.js API wrapper for interacting with Google's Gemini Flash model using the `@google/genai` SDK.

## Features

- **Text Generation**: Generate text from text prompts.
- **Image Analysis**: Generate insights or descriptions from images.
- **Document Analysis**: Summarize or query PDF/text documents.
- **Audio Analysis**: Transcribe or analyze audio files.

## Prerequisites

- Node.js (v18+ recommended)
- A Google Gemini API Key

## Installation

1. Clone the repository.
2. Install dependencies:
   ```bash
   npm install
   ```
3. Create a `.env` file in the root directory and add your API key:
   ```env
   GEMINI_API_KEY=your_api_key_here
   ```

## Usage

Start the server:

```bash
node index.js
```

The server will start on `http://localhost:3000`.

## API Endpoints

### 1. Generate Text

**Endpoint:** `POST /generate-text`

**Body:**
```json
{
  "prompt": "Explain Quantum Physics in simple terms"
}
```

### 2. Generate from Image

**Endpoint:** `POST /generate-from-image`

**Headers:** `Content-Type: multipart/form-data`

**Fields:**
- `image`: The image file.
- `prompt`: (Optional) Text prompt.

### 3. Generate from Document

**Endpoint:** `POST /generate-from-document`

**Headers:** `Content-Type: multipart/form-data`

**Fields:**
- `document`: The document file (e.g., PDF).
- `prompt`: (Optional) Query about the document. Defaults to summary request.

### 4. Generate from Audio

**Endpoint:** `POST /generate-from-audio`

**Headers:** `Content-Type: multipart/form-data`

**Fields:**
- `audio`: The audio file.
- `prompt`: (Optional) Query about the audio. Defaults to transcription request.

## Dependencies

- `express`: Web server framework.
- `multer`: Middleware for handling `multipart/form-data`.
- `dotenv`: Loads environment variables.
- `@google/genai`: Google Gemini AI SDK.
