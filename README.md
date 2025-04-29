# 🎮 Game Video Script & Thumbnail Generator

This project is a collaborative AI-driven system designed to **automatically generate scripts and thumbnails** for YouTube videos about videogames using the [Crew AI](https://github.com/joaomdmoura/crewai) framework.

## 🚀 Features

- Generates **structured scripts** for gaming-related YouTube videos.
- Creates **three thumbnail image prompts** inspired by the video content.
- Uses **multiple AI agents** (Scriptwriter, Thumbnail Creator, Reviewer) for task division.
- Utilizes **OpenAI GPT-4** and **DALL·E**, along with DuckDuckGo for web searches.
- Environment managed via `.env` file to safely load sensitive API keys.

---

## 📁 Project Structure

### 👨‍💼 Agents

1. **Scriptwriter**
   - Writes a YouTube-ready video script using web searches.
   - Delivers a clear structure with Introduction, Main Topic, and Conclusion.

2. **Thumbnail Creator**
   - Produces 3 creative prompts for generating different thumbnails.
   - Prompts are based on both the script and topic, using artistic variation.

3. **Reviewer**
   - Reviews the script and improves it if necessary.
   - Merges the script with generated thumbnails into a final markdown output.

---

## 🛠️ Requirements

Install required libraries with:

```bash
pip install crewai crewai-tools langchain-openai duckduckgo-search langchain-community python-dotenv
```

---

## 🔐 Environment Variables

Create a `.env` file in the project directory and add your OpenAI API key:

```
OPENAI_API_KEY=your_api_key_here
```

Then load the environment variables in the notebook using:

```python
%load_ext dotenv
%dotenv
```

---

## ▶️ How to Run

You can run the pipeline by passing a query like this:

```python
result = crew.kickoff(inputs={"query": "Top games of 2020"})
```

The output will be a final Markdown document containing the script and thumbnail images.

---

## 🧪 Example Output

You will receive a structured YouTube script, followed by three thumbnail suggestions based on the topic provided.

---

## 📌 Notes

- Recommended to run this project in [Google Colab](https://colab.research.google.com/) for easier dependency management.
- Thumbnails are generated using prompts sent to DALL·E API (via CrewAI tools).
