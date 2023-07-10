sequenceDiagram
    participant browser
    participant server

    activate browser
    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note
    browser-->>server: Browser sends note in JSON format
    deactivate browser
    activate server
    server->>browser: 302 Redirect /exampleapp/notes
    deactivate server
    activate browser
    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/notes
    deactivate browser
    activate server
    server-->>browser: HTML document
    deactivate server

    Note right of browser : The browser fetches the notes page and renders it