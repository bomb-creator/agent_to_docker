---

# 🔮 LangChain + Google Gemini Minimal Example

This is a minimal example project that demonstrates how to use LangChain with Google's **Gemini 2.0 Flash** model using the `langchain[google-genai]` integration.

## 🚀 Features

* Lightweight setup using LangChain
* Connects to **Gemini 2.0 Flash** via Google GenAI
* Secure API key handling with `getpass`
* Sends a simple prompt (`"Hello, world!"`) to the model

## 📦 Installation

Make sure you have Python 3.8+ installed.

Install the required LangChain package with Google GenAI support:

```bash
pip install -qU "langchain[google-genai]"
```

## 🔐 Authentication

This project requires a **Google API key** to access the Gemini models. You can get your key from the [Google AI Studio](https://makersuite.google.com/app/apikey).

The key will be securely entered via the terminal prompt.

## 🧠 Usage

Here's the complete code to run the model:

```python
import getpass
import os

# Prompt for API key securely if not already set in environment
if not os.environ.get("GOOGLE_API_KEY"):
    os.environ["GOOGLE_API_KEY"] = getpass.getpass("Enter API key for Google Gemini: ")

from langchain.chat_models import init_chat_model

# Initialize the Gemini 2.0 Flash model
model = init_chat_model("gemini-2.0-flash", model_provider="google_genai")

# Send a prompt to the model
response = model.invoke("Hello, world!")

print(response)
```

## 📌 Notes

* If you're running this in a notebook, the `getpass` prompt will show in the input cell.
* You can also set the API key ahead of time:

```bash
export GOOGLE_API_KEY="your-key-here"
```

## 📚 Resources

* [LangChain Docs](https://docs.langchain.com/)
* [Google GenAI Models](https://cloud.google.com/vertex-ai/docs/generative-ai/overview)

---

Let me know if you'd like this extended into a full example app or agent!
