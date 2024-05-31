sequenceDiagram
    participant Browser
    participant Server
    
    browser->>Server: GET https://studies.cs.helsinki.fi/exampleapp/notes
    activate server
    server -->>browser: HTML document
    deactivate server
    
    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    activate server
    server-->>browser: the css file
    deactivate server

    Note right of browser: The User adds data into the the form and clicks on the submit button initiatina a post command

    browser->server: POST {Form information}
    activate server
    server-->browser: REDIRECT 302
    deactivate server 
    
    browser->server: GET https://studies.cs.helsinki.fi/exampleapp/notes
    activate server
    server -->>browser: HTML document
    deactivate server
    
    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.js
    activate server
    server-->>browser: the JavaScript file
    deactivate server
    
    
    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server
    server-->>browser: [{ "content": "HTML is easy", "date": "2023-1-1" }, ... ]
    deactivate server    
