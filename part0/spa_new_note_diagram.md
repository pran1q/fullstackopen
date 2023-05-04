
```mermaid
sequenceDiagram
    participant browser
    participant server

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa
    activate server
    server-->>browser: HTTP 201, new_note_spa (application/json)
    deactivate server

    Note right of browser: The browser stays on the same page, the server does not ask for a redirect