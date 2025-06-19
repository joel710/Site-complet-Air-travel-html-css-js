# UML Use Case Diagram Description

## Actors

1.  **Client:** An individual using the platform to find and book travel.
2.  **Agent:** An employee of the travel agency (can represent various internal roles like Administrator, Accountant, or Booking Agent for this high-level overview).

## Use Cases

### Client Use Cases:
*   **UC1: Search for Flights/Destinations**
    *   Actor: Client
    *   Description: The client searches for available flights or browses destinations.
*   **UC2: Make Reservation**
    *   Actor: Client
    *   Description: The client selects a flight/package and books it, providing necessary details.
    *   Includes: UC10 (Provide Client Information)
*   **UC3: View Own Reservations**
    *   Actor: Client
    *   Description: The client views their current and past reservations and their statuses.
*   **UC4: Manage Own Profile**
    *   Actor: Client
    *   Description: The client updates their personal information (name, contact details).
*   **UC5: Make Payment**
    *   Actor: Client
    *   Description: The client makes a payment for a reservation.
*   **UC6: View Own Payment History**
    *   Actor: Client
    *   Description: The client views their past payments and associated invoices.
*   **UC7: Register Account**
    *   Actor: Client (New)
    *   Description: A new client creates an account on the platform.

### Agent Use Cases (encompassing Admin/Operational functionalities):
*   **UC8: Manage Clients**
    *   Actor: Agent
    *   Description: Agent performs CRUD operations (Create, Read, Update, Delete) on client accounts and views their travel history.
    *   Includes: UC10 (Provide Client Information)
*   **UC9: Manage Reservations**
    *   Actor: Agent
    *   Description: Agent can create, view, update the status of (e.g., confirm, cancel), and delete reservations.
*   **UC11: Manage Flights**
    *   Actor: Agent
    *   Description: Agent performs CRUD operations on flights, including adding new flights, modifying schedules, prices, and available seats, and deleting flights.
*   **UC12: Manage Destinations**
    *   Actor: Agent
    *   Description: Agent performs CRUD operations on travel destinations.
*   **UC13: Manage Payments & Invoices**
    *   Actor: Agent
    *   Description: Agent views overall payment history (filterable by client, agent, date range) and manages invoice generation (though generation is specified as automatic upon reservation validation).
*   **UC14: Manage Agents (User Management - typically Admin role)**
    *   Actor: Agent (Admin role)
    *   Description: An administrator manages agent accounts (add, modify, delete, assign roles/permissions).
*   **UC15: View System Reports/Statistics (Admin/Comptable role)**
    *   Actor: Agent (Admin/Comptable role)
    *   Description: Agent views overall system statistics, financial reports, and other analytical data.

### Supporting Use Cases:
*   **UC10: Provide Client Information** (Supporting use case for UC2, UC7, UC8)
    *   Actors: Client, Agent
    *   Description: Client (during registration/profile update) or Agent (during client management) provides or updates client details.

## Relationships Summary

*   **Client** is associated with UC1, UC2, UC3, UC4, UC5, UC6, UC7.
*   **Agent** is associated with UC8, UC9, UC11, UC12, UC13, UC14, UC15.
*   **UC2 (Make Reservation)** includes UC10 (Provide Client Information).
*   **UC8 (Manage Clients)** includes UC10 (Provide Client Information).
*   **UC7 (Register Account)** includes UC10 (Provide Client Information).

**Note:** This is a textual description. A graphical UML diagram would visually represent these actors, use cases, and their relationships.
