# 🚀 Advancing Hate Speech Detection: A Multilingual System Using Llama-2 For Real-Time Analysis Of Audio and Video Content

This project is a sophisticated application designed to detect hate speech in multiple languages from various sources, including text, audio files, video files, and real-time microphone input. It leverages a fine-tuned Llama-2 model to provide accurate, real-time analysis, all wrapped in a user-friendly web interface built with Streamlit.

---

## 👥 Team Members

- **Naveen B** - [GitHub Profile](https://github.com/sir-zech)
- **Mouli Monish S** - [GitHub Profile](https://github.com/moulimonishxx)
- **Nimalan R** - [GitHub Profile](https://github.com/your-username)
- **Srivathsan C.B** - [GitHub Profile](https://github.com/Sri1012)

---

## ✨ Features

- **🌐 Multi-lingual Support:** Capable of detecting hate speech in various languages.
- **⏱️ Real-time Analysis:** Provides instant feedback on audio and text inputs.
- **🎤 Versatile Input Methods:**
  - **✍️ Text Input:** Directly enter and analyze text for hate speech.
  - **🎵 Audio File Upload:** Upload audio files (e.g., MP3, WAV) for transcription and analysis.
  - **🎬 Video File Upload:** Upload video files (e.g., MP4) to extract audio, transcribe it, and analyze for hate speech.
  - **▶️ YouTube Video Analysis:** Analyze spoken content from YouTube videos by simply providing the URL.
  - **🎙️ Live Microphone Input:** Capture and analyze speech directly from your microphone in real-time.
- **🔒 User Authentication:** Secure login and signup system for personalized user experience.

---

## 🛠️ Getting Started

Follow these instructions to set up and run the project on your local machine.

### 📝 Prerequisites

- **Python 3.10:** It is **highly recommended** to use Python version 3.10, as it is the most stable version for the dependencies used in this project.
- **pip:** Python package installer.
- **ffmpeg:** A cross-platform solution to record, convert and stream audio and video.

### 📥 Installation

1.  **Clone the repository:**

    ```bash
    git clone <repository-url>
    cd <repository-directory>
    ```

2.  **Install FFmpeg:**
    This project requires FFmpeg for processing audio from video files.

    - **Windows:**
      1.  Download the latest static build from the [FFmpeg website](https://ffmpeg.org/download.html).
      2.  Extract the downloaded archive (e.g., to `C:\`).
      3.  Add the `bin` directory from the extracted folder (e.g., `C:\ffmpeg\bin`) to your system's PATH environment variable.
      4.  Verify the installation by opening a new command prompt and typing `ffmpeg -version`.
    - **macOS (using Homebrew):**
      ```bash
      brew install ffmpeg
      ```
    - **Linux (using apt):**
      ```bash
      sudo apt update
      sudo apt install ffmpeg
      ```

3.  **Create a virtual environment (recommended):**

    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
    ```

4.  **Install Python dependencies:**
    All the required Python libraries are listed in the `requirements_updated.txt` file. Install them using pip:

    ```bash
    pip install -r requirements_updated.txt
    ```

### ▶️ Running the Application

Once you have completed the installation steps, you can run the application using Streamlit.

1.  Navigate to the project's root directory in your terminal.
2.  Run the following command:
    ```bash
    streamlit run app.py
    ```
3.  The application will start, and you can access it in your web browser at the local URL provided in the terminal (usually `http://localhost:8501`).

---

## 📂 File Descriptions

- **`app.py`**: The main application file that runs the Streamlit web interface. It handles user input, processes audio/video, and displays the hate speech detection results.
- **`training1.ipynb`**: A Jupyter Notebook containing the code and process for training the hate speech detection model.
- **`test.ipynb`**: A Jupyter Notebook used for testing and evaluating the performance of the trained model.
- **`requirements_updated.txt`**: A list of all Python packages and their versions required to run the project.
- **`data.json`**: A JSON file that acts as a simple database for user authentication, storing user information.
- **Model Files (`config.json`, `special_tokens_map.json`, `spiece.model`, `tokenizer.json`, `tokenizer_config.json`)**: These files define the architecture, vocabulary, and configuration of the pre-trained Llama-2 model used for the hate speech detection task.

---

## ⚙️ How It Works

The application uses a multi-step process to detect hate speech:

1.  **📥 Input:** The user provides input in the form of text, an audio file, a video file, a YouTube URL, or live speech.
2.  **🗣️ Transcription:** For audio and video inputs, the audio is first extracted and then transcribed into text using the `whisper` library.
3.  **🔄 Preprocessing:** The transcribed or directly entered text is formatted into a prompt suitable for the Llama-2 model.
4.  **🧠 Inference:** The prompt is fed into the fine-tuned Llama-2 model, which classifies the text as either containing hate speech or not.
5.  **📊 Output:** The result of the classification is displayed to the user in the web interface, along with a confidence score.

This system provides a powerful and accessible tool for identifying and moderating harmful content in various forms of media.
