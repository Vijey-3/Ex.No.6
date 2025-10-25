# **Ex. No. 6: Development of Python Code Compatible with Multiple AI Tools**

**Date:**
**Register No.:**

## **Title:**

Framing Prompts for AI-Assisted Project Coding

---

## **Aim:**

To develop and execute Python code that integrates with multiple AI tools to automate interactions with APIs, compare their outputs, and generate meaningful insights. The experiment focuses on designing structured prompts that help AI tools assist effectively in coding tasks related to project development.

---

## **Objective:**

The objective of this experiment is to enable learners to:

1. Understand how to frame effective and clear prompts for AI tools to perform Python coding tasks.
2. Generate Python scripts that can connect and interact with multiple APIs.
3. Compare outputs from various APIs and identify differences or similarities.
4. Interpret results and generate actionable insights or recommendations.
5. Evaluate and refine prompt quality to improve AI-assisted development outcomes.

---

## **Tools and Technologies Required:**

* Python 3.x
* Any AI Code Assistant (ChatGPT, GitHub Copilot, Google Gemini, etc.)
* Internet access for API integration
* Libraries: `requests`, `json`, `pandas`, `matplotlib` (if visualization is needed)

---

## **AI Tools Used:**

1. **ChatGPT** – for code generation and explanation.
2. **Google Gemini / Copilot** – for comparison and alternate code suggestions.

---

## **Exercise Description:**

In this experiment, instead of manually coding from scratch, students will **design structured prompts** to instruct AI tools in generating Python code for specific tasks.
The exercise is divided into three stages:

### **Stage 1: Interacting with Multiple APIs**

* The prompt should ask the AI tool to generate Python code that connects to two or more APIs (e.g., weather APIs, news APIs, or currency exchange APIs).
* The code should fetch and display JSON responses from both sources.

**Example Prompt:**

> "Write a Python script that connects to two public APIs – OpenWeatherMap and WeatherAPI. Fetch the current temperature and weather condition for a given city from both APIs and print the results."

---

### **Stage 2: Comparing Outputs from Different APIs**

* The prompt should guide the AI to generate code that compares the responses from both APIs.
* It should identify differences in values (like temperature, humidity, or description).

**Example Prompt:**

> "Generate a Python program that compares temperature and humidity values retrieved from OpenWeatherMap and WeatherAPI for the same location. Display the difference in values in a tabular format."

---

### **Stage 3: Generating Actionable Insights**

* The prompt should make the AI analyze differences and suggest insights or next steps.
* For instance, if the APIs show differing values, the AI can recommend which API seems more reliable or when to recheck the data.

**Example Prompt:**

> "Create Python code that analyzes the difference between two API outputs (weather data) and generates insights like 'API 1 is reporting higher temperature – possible server delay in API 2' or 'Both APIs show similar humidity – data consistency confirmed'."

---

## **AI-Generated Output (Sample Response):**

```python
import requests

city = "Chennai"
api1 = f"https://api.openweathermap.org/data/2.5/weather?q={city}&appid=YOUR_API_KEY"
api2 = f"https://api.weatherapi.com/v1/current.json?key=YOUR_API_KEY&q={city}"

data1 = requests.get(api1).json()
data2 = requests.get(api2).json()

temp1 = data1['main']['temp'] - 273.15
temp2 = data2['current']['temp_c']
humidity1 = data1['main']['humidity']
humidity2 = data2['current']['humidity']

print(f"OpenWeatherMap - Temp: {temp1:.2f}°C, Humidity: {humidity1}%")
print(f"WeatherAPI - Temp: {temp2:.2f}°C, Humidity: {humidity2}%")

if abs(temp1 - temp2) > 2:
    print("Noticeable temperature difference detected between APIs.")
else:
    print("Temperature data seems consistent between APIs.")
```

---

## **Explanation:**

This experiment applies **Prompt Engineering** to guide multiple AI tools in code generation. The same task prompt was tested across two AI platforms (e.g., ChatGPT and Gemini).

* **ChatGPT** provided structured and modular Python code with explanations.
* **Gemini** suggested a similar approach but with different error-handling and data extraction methods.
  By comparing both outputs, students can evaluate which AI generated more optimized and readable code.

---

## **Reflection Note:**

Through this experiment, I learned how small changes in prompt phrasing can significantly impact the quality and structure of AI-generated code.

* A well-structured prompt yields clean, modular, and well-commented code.
* Adding context like “use requests and JSON library” or “display output in tabular form” helps AI produce more relevant code.
* Comparing outputs from multiple AI tools improves understanding of code diversity and optimization.

In future, I would refine my prompts by specifying constraints such as error handling, API key security, and data visualization for better automation.

---

## **Conclusion:**

The experiment successfully demonstrated how **Prompt Engineering** can be used to instruct AI tools to generate functional and comparable Python code. It highlights the importance of prompt clarity and iterative refinement when using multiple AI systems for software development tasks.

---

## **Result:**

The corresponding prompts were executed successfully, and the Python code integrating multiple APIs was generated and analyzed using multiple AI tools.

---

