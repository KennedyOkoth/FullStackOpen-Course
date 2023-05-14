```mermaid
sequenceDiagram
    participant user
    participant browser
    participant API
    participant server
    participant database

    user->>browser: Clicks the notes button on the UI
    browser->>API: sends an AJAX request to create a new note
    API->>server: Processes a new note creation request
    server->>database: Stores the new note
    database-->>server: Returns a successful note creation message
    server-->>API: Returns a successful note creation message
    API-->>browser: Returns a successful note creation message
    browser-->>user: displays a succesfull message