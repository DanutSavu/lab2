# 🎬 Cinema Use Case Diagram

This project represents a simple **Cinema System** using UML Use Case Diagram.

## Actors

* Client
* Admin

## Use Cases

Client can:

* View Movies
* Buy Ticket
* Cancel Ticket

Admin can:

* Add Movie
* Remove Movie

## Relationships

* Buy Ticket **<<include>>** Select Seat
* Buy Ticket **<<include>>** Process Payment
* Apply Discount **<<extend>>** Buy Ticket

## Diagram

![Cinema UML Diagram](cinema-diagram.png)
