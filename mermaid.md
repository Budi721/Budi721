sequenceDiagram
    participant Backend
    participant AI
    participant Topic
    participant MessageStorage

    Backend->>AI: Mengirim camera id sebagai param name
    AI-->>Backend: Generate topic zappy.license_plate_recognition.<name stream>
    Backend->>Topic: Mengirim message ke topic tersebut
    Backend->>MessageStorage: Subscribe ke message
    Topic-->>Backend: Menerima message
    Backend->>Backend: Extract camera id from topic
    Backend->>MessageStorage: Save message
