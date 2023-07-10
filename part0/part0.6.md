```mermaid
sequenceDiagram
    participant browser
    participant server

    loop
    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa
    browser-->>server: Browser sends note in JSON format
    server->>browser: 201 Created
     Note right of browser: Browser executes JS to render the  new page
     Note left of server: Server updates the database with new note
    end