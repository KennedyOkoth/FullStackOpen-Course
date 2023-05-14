```mermaid
sequenceDiagram
    autonumber
    participant User
    participant Browser
    participant API
    participant Server

    User->>Browser: Interacts with the UI
    Browser->>API: Sends AJAX request
    API->>Server: Request processing
    Server-->>API: Returns data
    API-->Browser: Returns data as JSON
    Browser-->>User: Displays the page using the data returned
    User->>Browser: Clicks a button
    Browser->>API: Sends a second AJAX request
    API->>Server: Request processing for the seconnd time
    Server-->>API: Returns updated data
    API-->Browser: Returns updated data as JSON
    Browser-->>User: Displays the page using updated data returned