**HBnB Architecture**

**Overview**

This repository contains the architectural design and technical documentation for the HBnB application. The goal of this project is to define a clear and maintainable system structure using layered architecture principles.

The design separates responsibilities across different layers and uses the Facade pattern to simplify interactions between components.

---

**Architecture Summary**

The system is organized into three main layers:

- **Presentation Layer** – Handles API endpoints and user interaction
- **Business Logic Layer** – Contains core models and application logic
- **Persistence Layer** – Manages data storage and retrieval

A **Facade** is used as a central interface between the Presentation Layer and the Business Logic Layer.

---

**Diagrams**

The project includes the following diagrams:

- High-Level Package Diagram
- Business Logic Class Diagram
- API Sequence Diagrams

**Full technical documentation:**
./technical_document.md

---

**Technologies Used**

- Mermaid.js (for diagrams)
- Markdown (for documentation)
- Git & GitHub (version control)

---

**Project Structure  **

hbnb-architecture/  
│  
├── README.md  
└── technical_document.md  

---

**Purpose**

This repository serves as a reference for system design and will guide future implementation phases of the HBnB application.

---

**Author**

Uzair Jahangirov