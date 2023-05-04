
```mermaid
sequenceDiagram
    participant browser
    participant server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/spa
    activate server
    server-->>browser: spa (text/html)
    deactivate server

    Note right of browser: The browser parses spa file `<link rel="stylesheet" type="text/css" href="/exampleapp/main.css" />`

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    activate server
    server-->>browser:  main.css (text/css)
    deactivate server

    Note right of browser: The browser parses spa file `<script type="text/javascript" src="/exampleapp/main.js"></script>`

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/spa.js
    activate server
    server-->>browser: spa.js (application/javascript)
    deactivate server

    Note right of browser: The browser starts executing the JavaScript code that fetches the JSON from the server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server
    server-->>browser: data.json (application/json)
    deactivate server

    Note right of browser: The browser executes the callback function that renders the notes