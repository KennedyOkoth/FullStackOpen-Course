```mermaid
sequenceDiagram
    autonumber
    participant User
    participant browser
    participant server
    participant Database

    User->>browser: clicks on notes link
    browser->>server: GET GET https://studies.cs.helsinki.fi/exampleapp/notes
    activate server
    server-->>browser: HTML document
    deactivate server

    activate browser
    browser-->>User: Notes text field
    deactivate browser
    User->>browser: Submits notes
    browser->>server: POST request
    server->>Database: Saves the POST request
    activate Database
    Database-->>server: Response
    deactivate Database

    activate server
    server-->>browser: Updated HTML document
    deactivate server

    activate browser
    browser-->>User: Displays new notes
    deactivate browser