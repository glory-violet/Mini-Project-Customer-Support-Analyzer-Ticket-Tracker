# Mini-Project-Customer-Support-Analyzer-Ticket-Tracker
Organizations often struggle to manage incoming customer requests efficiently. Support teams receive a high volume of messages via email, chat, and calls, making it hard to:

- Track open tickets
- Assign tickets to the right agent
- Analyze sentiment (happy, angry, neutral)
- Prioritize urgent issues

This project helps automate ticket assignment, basic sentiment analysis, and workflow visualization for better customer support management.

---

## Features & Functional Requirements

### Features
1. **Ticket Creation:** Automatically capture customer requests.
2. **Sentiment Analysis:** Classify messages as positive, neutral, or negative.
3. **Automated Assignment:** Assign tickets to available agents.
4. **Status Tracking:** Keep track of pending, in-progress, and resolved tickets.
5. **Basic Reporting:** Count of tickets per agent and sentiment summary.

### Functional Requirements
- Python backend for ticket management
- Optional integration with CSV or JSON to store ticket data
- Simple command-line interface to simulate ticket workflow
- Visualization of workflow using a diagram

---

## Workflow Diagram

![Ticket Workflow Diagram](workflow_diagram.png)

*Workflow Explanation:*
1. Customer sends a message.
2. Message is analyzed for sentiment.
3. Ticket is created in the system.
4. Ticket is assigned to an available agent.
5. Agent updates ticket status (in-progress → resolved).
6. System generates basic reports.

---

## How I Approached PRD Creation
- **Step 1: Define Problem** – Identified inefficiencies in customer support ticket management.
- **Step 2: List Requirements** – Captured both functional (ticket assignment, reporting) and non-functional (simple CLI, Python-based) requirements.
- **Step 3: Prioritize Features** – Focused on core workflow: capture → analyze → assign → track → report.
- **Step 4: Visualize Workflow** – Created a workflow diagram to simplify development steps.
- **Step 5: Implement Prototype** – Built a small Python script to simulate ticket creation and assignment.

---

## Python Simulation Script

```python
import random

# Sample agents
agents = ["Alice", "Bob", "Charlie"]

# Sample tickets
tickets = [
    {"id": 1, "message": "My software crashed!", "status": "pending"},
    {"id": 2, "message": "Need help with login.", "status": "pending"},
    {"id": 3, "message": "Feature request: dark mode.", "status": "pending"},
]

# Simple sentiment analysis (simulated)
def analyze_sentiment(message):
    if "crash" in message or "error" in message:
        return "negative"
    elif "help" in message:
        return "neutral"
    else:
        return "positive"

# Assign tickets to random agents
for ticket in tickets:
    ticket["sentiment"] = analyze_sentiment(ticket["message"])
    ticket["assigned_to"] = random.choice(agents)
    ticket["status"] = "in-progress"
    print(f"Ticket {ticket['id']} assigned to {ticket['assigned_to']} | Sentiment: {ticket['sentiment']} | Status: {ticket['status']}")

# Mark tickets as resolved
for ticket in tickets:
    ticket["status"] = "resolved"
    print(f"Ticket {ticket['id']} resolved by {ticket['assigned_to']}")
