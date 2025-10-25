
---

# **Ex.No.6 Development of Python Code Compatible with Multiple AI Tools**

**Date:** 25-10-2025
**Register No.:** 212223040239

---

## **Aim**

To write and implement a Python program that interacts with multiple AI tools (OpenAI’s GPT and Google’s Gemini) to automate Python code generation, analyze the quality of responses, and derive meaningful insights. The experiment applies the *persona pattern* to instruct the AI models to act as professional programmers for a specific coding task, allowing comparative study of code efficiency, readability, and reliability.

---

## **Algorithm**

**Input:** A structured persona-based prompt describing a coding task.
**Output:** Comparative performance analysis of multiple AI-generated code outputs.

**Steps:**

1. Define the AI task to be automated (e.g., text summarization, web scraping, or data visualization).
2. Frame a **persona-based prompt**, such as *“Act as an expert Python developer. Generate optimized and commented code for…”*
3. Initialize and authenticate API connections for OpenAI and Google Gemini.
4. Send the prompt to the first AI model (ChatGPT/GPT-4) and record the generated response.
5. Send the same prompt to the second AI model (Gemini Pro) and store its output.
6. Execute or analyze both generated codes for functional correctness.
7. Compare both outputs for:

   * Code readability
   * Accuracy and logic
   * Adherence to best practices
   * Error-handling and efficiency
8. Generate a **comparative report** or table summarizing the findings.
9. Formulate insights on which AI performs better for the defined use case.

---

## **AI Tools & Libraries Required**

**AI Models:**

* OpenAI GPT-4 or GPT-3.5 Turbo
* Google Gemini Pro

**Python Libraries:**

* `openai` → for OpenAI API communication
* `google-generativeai` → for Gemini API access
* `requests` → for web requests
* `beautifulsoup4` → for HTML parsing
* `os`, `json`, `dotenv` → for configuration and environment variable management

**Software Requirements:**

* Python 3.8 or higher
* IDE: Visual Studio Code / PyCharm
* Valid API keys for both OpenAI and Google AI Studio

---

## **Explanation**

### **Introduction**

AI-assisted programming has become an essential skill for modern developers. Tools like ChatGPT and Gemini can generate, refactor, or explain code with minimal input from the user. However, their outputs differ depending on model architecture and training datasets.

This experiment explores how to send identical prompts to multiple AI tools, analyze their code generation behavior, and identify which produces cleaner, more reliable code.

By applying the **persona pattern**, the AI is guided to *think and respond like an expert programmer*, improving the accuracy, structure, and practicality of the generated script.

---

## **Key Concepts**

### 1. **API Integration**

API (Application Programming Interface) allows communication between Python and AI tools. Developers send a prompt as a **JSON request**, and the API responds with **model-generated text/code**.

**Flow:**
Python → API Request → AI Model → JSON Response → Output Display

---

### 2. **Persona Pattern**

A persona-based prompt defines the *role* the AI should assume.
Example:

* Generic: “Write a Python code for weather forecasting.”
* Persona: “Act as a senior Python developer specializing in data science. Write efficient and commented code for weather forecasting using an API.”

This technique enhances output clarity, coding best practices, and contextual relevance.

---

### 3. **Multi-Tool Comparison**

Different AI models produce varied outputs for the same prompt due to internal design differences. Comparing them helps determine:

* Which AI provides better syntax and readability
* Which handles edge cases more effectively
* Which offers more maintainable code

---

## **Concept: Persona Pattern 👨‍💻**

The persona pattern transforms simple AI queries into **context-rich instructions**. By giving AI a role, it assumes domain expertise.

Example persona:

> “Act as an experienced Python developer in data scraping and analysis. Write optimized, error-free, and reusable code.”

This ensures consistent, logical, and production-ready outputs.

---

## **Application Scenario**

The assigned task:

> *Develop a Python program that scrapes top news headlines from BBC News ([https://www.bbc.com/news](https://www.bbc.com/news)) using requests and BeautifulSoup.*

This real-world problem involves fetching live web data, making it ideal for evaluating how AI tools handle networking, HTML parsing, and error management.

---

## **Methodology**

1. Define the task clearly in natural language.
2. Frame a detailed persona-based prompt.
3. Use a Python controller script to send the same prompt to GPT and Gemini APIs.
4. Receive and store the generated code from both models.
5. Execute and test each version for performance and correctness.
6. Record findings and summarize differences.

---

## **Implementation: Master Python Script**

```python
import os
import openai
import google.generativeai as genai

OPENAI_API_KEY = os.getenv("OPENAI_API_KEY")
GEMINI_API_KEY = os.getenv("GEMINI_API_KEY")

openai.api_key = OPENAI_API_KEY
genai.configure(api_key=GEMINI_API_KEY)

prompt = """
Act as an expert Python developer specializing in web scraping.
Write a complete, efficient Python script that fetches and displays
the top headlines from BBC News (https://www.bbc.com/news)
using requests and BeautifulSoup. Include error handling and comments.
"""

def get_openai_response(prompt):
    response = openai.chat.completions.create(
        model="gpt-4",
        messages=[{"role": "system", "content": "You are an expert Python programmer."},
                  {"role": "user", "content": prompt}]
    )
    return response.choices[0].message.content.strip()

def get_gemini_response(prompt):
    model = genai.GenerativeModel('gemini-pro')
    response = model.generate_content(prompt)
    return response.text.strip()

if __name__ == "__main__":
    print("Fetching responses from both AI tools...\n")
    gpt_code = get_openai_response(prompt)
    gemini_code = get_gemini_response(prompt)

    print("\n--- Code by OpenAI GPT ---\n")
    print(gpt_code)
    print("\n--- Code by Google Gemini ---\n")
    print(gemini_code)
```

---

## **Sample Outputs**

### **Output from ChatGPT**

* Uses specific CSS selectors with `data-testid`
* Implements `User-Agent` for web scraping safety
* Employs concise `raise_for_status()` for error handling

### **Output from Gemini**

* Uses general HTML selectors with `a.gs-c-promo-heading`
* Includes timeout handling and specific exceptions
* Provides detailed console logs and step-by-step process indicators

---

## **Analysis and Discussion**

| Criteria               | ChatGPT (OpenAI GPT)              | Gemini (Google)                               |
| ---------------------- | --------------------------------- | --------------------------------------------- |
| **Selector Precision** | Highly specific (uses test IDs)   | Generalized selectors                         |
| **Error Handling**     | Compact with `raise_for_status()` | Detailed with `Timeout` and `ConnectionError` |
| **Code Readability**   | More concise and professional     | Verbose but beginner-friendly                 |
| **Best Practice**      | Adds `User-Agent`                 | Adds `timeout`                                |
| **Execution Speed**    | Fast due to minimal checks        | Slightly slower but more robust               |
| **Output Clarity**     | Cleanly formatted headlines       | Descriptive with extra logs                   |

Both tools followed professional coding practices but displayed unique priorities: ChatGPT prioritized clean structure, while Gemini focused on stability and user awareness.

---

## **Flowchart**

```
+------------------+
|  Define Prompt   |
+------------------+
         |
         v
+----------------------+
| Send Prompt to GPT   |
+----------------------+
         |
         v
+----------------------+
| Send Prompt to Gemini|
+----------------------+
         |
         v
+----------------------------+
| Collect and Compare Outputs|
+----------------------------+
         |
         v
+--------------------+
| Generate Insights  |
+--------------------+
```

---

## **Applications**

* **Software Development:** Auto-generate boilerplate or repetitive code.
* **Data Analysis:** Compare NLP outputs (summarization, classification).
* **Education:** Teach AI model behavior and coding styles.
* **Research:** Evaluate AI consistency across coding tasks.

---

## **Limitations**

* Requires stable internet and valid API keys.
* Model outputs may vary across executions.
* Some AI tools lack strict persona adherence.
* Paid APIs can be cost-prohibitive for extended testing.

---

## **Future Enhancements**

* Include third AI models (e.g., Claude, Cohere).
* Add visual charts comparing execution time and accuracy.
* Automate performance scoring metrics (e.g., runtime, lines of code).
* Create a unified dashboard for real-time AI comparison.

---

## **Deliverables**

* Python script for multi-AI integration.
* AI-generated codes (OpenAI & Gemini).
* Comparative analysis table.
* Insights on persona-based prompt effectiveness.

---

## **Conclusion**

This experiment successfully demonstrates the power of **Prompt Engineering** in AI-assisted programming.
By using persona-based prompts and integrating multiple AI APIs, we achieved:

* Comparative understanding of AI-generated coding styles.
* Insight into best practices (headers, timeouts, error handling).
* Automation of coding and evaluation tasks.

It proves that developers now play a *supervisory and integrative role* — refining, validating, and merging the best outputs from various AI models to create optimal software solutions.

---

## **Result:**

Thus, the **Development of Python Code Compatible with Multiple AI Tools** was successfully executed and analyzed.

---
