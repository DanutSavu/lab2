Cinema System - Use Case Diagram

```mermaid
flowchart LR

Client((Client))
Admin((Admin))

ViewMovies[View Movies]
BuyTicket[Buy Ticket]
SelectSeat[Select Seat]
ProcessPayment[Process Payment]
ApplyDiscount[Apply Discount]
CancelTicket[Cancel Ticket]

AddMovie[Add Movie]
RemoveMovie[Remove Movie]

Client --> ViewMovies
Client --> BuyTicket
Client --> CancelTicket

Admin --> AddMovie
Admin --> RemoveMovie

BuyTicket -->|<<include>>| SelectSeat
BuyTicket -->|<<include>>| ProcessPayment

ApplyDiscount -.->|<<extend>>| BuyTicket
CancelTicket -.->|<<extend>>| BuyTicket
```

## Actors

* Client
* Admin

## Main Use Cases

Customer can:

* View movies
* Buy tickets
* Cancel tickets

Admin can:

* Add movies
* Remove movies

## Relationships

* **Buy Ticket <<include>> Select Seat**
* **Buy Ticket <<include>> Process Payment**
* **Apply Discount <<extend>> Buy Ticket**
* **Cancel Ticket <<extend>> Buy Ticket**

