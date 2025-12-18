# SAP QA Copilot – AI-driven Testing Assistant

SAP QA Copilot is a backend application designed to support Quality Assurance and testing teams by automatically analyzing system logs and generating structured QA insights.  
The project focuses on simplicity, clarity, and real-world enterprise use cases, especially in SAP environments.

This project is developed as part of the **SAP Business AI Innovation Challenge**.

---

## 🚀 Project Goal

The main goal of SAP QA Copilot is to help testers and QA engineers:

- analyze large volumes of system logs
- quickly detect errors, warnings, and informational messages
- generate structured QA summaries
- build a foundation for future AI-driven test analysis and reporting

The project is intentionally built step by step, starting with core logic before adding AI capabilities.

---

## 🧠 How It Works (High-Level)

1. A user sends system logs to the backend via an API request.
2. The application validates the input data.
3. Logs are analyzed using simple QA logic (error, warning, info detection).
4. A structured QA report is returned as a JSON response.

This approach reflects real-world QA workflows used in SAP support and testing teams.

---

## 🧱 Project Structure
```
app/
├── main.py # Application entry point
├── routes/ # API endpoints
│ └── analyze.py
├── models/ # Data validation models
│ └── log_entry.py
├── services/ # Business and QA logic
│ └── log_analyzer.py
└── core/ # Configuration and shared utilities
```


The project follows a clean separation of concerns:
- **routes** handle HTTP communication
- **models** validate input data
- **services** contain core QA logic

---

## 🔍 Example API Request

**POST** `/analyze/`

```json
{
  "system": "SAP S/4HANA",
  "environment": "QA",
  "logs": [
    "Error: RFC connection failed",
    "Warning: Authorization missing",
    "Info: User logged in"
  ]
}
```
Response:
```
{
  "system": "SAP S/4HANA",
  "environment": "QA",
  "analysis": {
    "errors": 1,
    "warnings": 1,
    "infos": 1,
    "total": 3
  }
}
```
## 🛠 Built With

Python 3.11
FastAPI – backend framework
Pydantic – data validation
Uvicorn – ASGI server
Virtualenv – local environment management

## 🎯 Why This Project Matters

Reflects real QA and SAP support scenarios
Focuses on understandable and maintainable logic
Designed for gradual extension with AI and SAP BTP services
Suitable for QA engineers transitioning into AI-assisted testing

## 🔮 Future Plans

Integrate SAP Business AI / Generative AI Hub
Add AI-based log interpretation and summarization
Generate test case suggestions from logs
Export QA reports to external tools (e.g. Jira, TestRail)
Extend support for SAP-specific logs (ABAP dumps, IDocs, RFC errors)

## 👤 Author

Marcin Gwara
QA Automation Engineer | AI-driven Testing Enthusiast

## 📄 License

This project is provided for educational and innovation purposes as part of the SAP Business AI Innovation Challenge.
