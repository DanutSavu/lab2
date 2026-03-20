```mermaid
useCaseDiagram
    actor Client
    actor Server

    package Cinema {
        usecase "Cumparare Bilet" as UC1
        usecase "Autentificare" as UC2
        usecase "Plata Online" as UC3
        usecase "Reducere Elev" as UC4
    }

    Client --> UC1
    UC1 ..> UC2 : <<include>>
    UC1 ..> UC3 : <<include>>
    UC1 <.. UC4 : <<extend>>
    UC3 --> Server
```
