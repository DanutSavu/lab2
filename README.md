Cinema Use Case Diagram

```mermaid
flowchart LR

Client((Client))
Admin((Admin))

ViewMovies((View Movies))
BuyTicket((Buy Ticket))
CancelTicket((Cancel Ticket))
SelectSeat((Select Seat))
ProcessPayment((Process Payment))
ApplyDiscount((Apply Discount))

AddMovie((Add Movie))
RemoveMovie((Remove Movie))

Client --> ViewMovies
Client --> BuyTicket
Client --> CancelTicket

Admin --> AddMovie
Admin --> RemoveMovie

BuyTicket -->|<<include>>| SelectSeat
BuyTicket -->|<<include>>| ProcessPayment

ApplyDiscount -.->|<<extend>>| BuyTicket
```

