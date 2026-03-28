# Mini Project: Ticket Management System

## Overview
This mini project is built around a **Product Requirement Document (PRD) + Workflow** to simulate a ticket management system. It demonstrates problem-solving, feature planning, and workflow design, with a small interactive Python script for ticket assignment.

---

## Problem It Solves
Many organizations struggle with tracking issues, requests, or tasks in a structured way. This project aims to:

- Provide a clear system for logging and assigning tickets.
- Ensure that issues are tracked and not lost in communication.
- Help small teams practice PRD-driven development.

---

## Features & Functional Requirements

### Features
- Add new tickets with title, description, and priority.
- Assign tickets to team members.
- Track ticket status: Open, In Progress, Completed.
- View all tickets in a structured format.

### Functional Requirements
1. Users can create a new ticket with necessary details.
2. Users can assign tickets to a specific team member.
3. Users can update the status of tickets.
4. The system should allow listing all tickets and filtering by status or assignee.

---

## Workflow Diagram
Below is the workflow for the ticket system:

<img width="336" height="575" alt="Image" src="https://github.com/user-attachments/assets/22cdb8e5-bcc0-4d2f-bfee-9c7f8b2f1012" />*Note: Replace this image path with your actual workflow diagram.*

**Workflow Steps:**
1. Ticket Creation → 2. Assignment → 3. Progress Tracking → 4. Completion → 5. Reporting

---

## PRD Approach
To create the PRD:
- Identified the **problem** with ticket management in small teams.
- Defined **user stories**: e.g., "As a team lead, I want to assign tickets to team members so that work is distributed efficiently."
- Listed **features and functional requirements** clearly.
- Drew a **workflow diagram** to visualize the ticket lifecycle.
- Added a **small interactive Python script** for demonstration.

---

## Optional Interactive Python Script
This script simulates ticket assignment:

```python
# ticket_manager.py

tickets = []

def create_ticket(title, assignee):
    ticket = {"id": len(tickets)+1, "title": title, "assignee": assignee, "status": "Open"}
    tickets.append(ticket)
    print(f"Ticket created: {ticket}")

def list_tickets():
    print("\nAll Tickets:")
    for t in tickets:
        print(f"{t['id']}. {t['title']} - {t['assignee']} - {t['status']}")

def update_status(ticket_id, status):
    for t in tickets:
        if t["id"] == ticket_id:
            t["status"] = status
            print(f"Ticket {ticket_id} status updated to {status}")

# Example usage
create_ticket("Fix login bug", "Alice")
create_ticket("Update README", "Bob")
list_tickets()
update_status(1, "In Progress")
list_tickets()
