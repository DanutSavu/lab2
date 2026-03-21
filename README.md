# 🎬 Cinema Ticket System

## Description

This project models a simple **Cinema Ticket System** using UML concepts and the **Repository design pattern**.
The system allows customers to view movies, buy tickets and process payments, while administrators manage movies.

---

# Actors

## Customer

A person who uses the cinema system to watch movies and buy tickets.

## Admin

A person responsible for managing the movies in the cinema system.

---

# Use Cases

### Customer

* View Movies
* View Movie Details
* Buy Ticket
* Select Seat
* Process Payment
* Apply Discount

### Admin

* Add Movie
* Remove Movie
* Update Movie

---

# Use Case Relationships

## <<include>>

Some actions are always executed as part of another action.

Example:

Buy Ticket
<<include>> Select Seat
<<include>> Process Payment

This means when a user buys a ticket, the system must also select a seat and process the payment.

---

## <<extend>>

Some actions are optional.

Example:

Apply Discount
<<extend>> Buy Ticket

This means the discount is applied only if the customer has a promotional code.

---

# Domain Classes

## Movie

Represents a movie available in the cinema.

Attributes:

* id
* title
* genre
* duration

## Ticket

Represents a cinema ticket.

Attributes:

* id
* movieId
* seatNumber
* price

## Customer

Represents a cinema user.

Attributes:

* id
* name
* email

---

# Repository Pattern

The **Repository Pattern** is used to separate the data access logic from the application logic.

Repositories store and retrieve data from collections.

---

# Example Repository Code

```csharp
public interface ITicketRepository
{
    void SaveTicket(Ticket ticket);
    Ticket FindTicket(int id);
}
```

```csharp
public class TicketRepository : ITicketRepository
{
    private List<Ticket> tickets = new List<Ticket>();

    public void SaveTicket(Ticket ticket)
    {
        tickets.Add(ticket);
    }

    public Ticket FindTicket(int id)
    {
        return tickets.FirstOrDefault(t => t.Id == id);
    }
}
```

---

# Example System Flow

1. Customer views available movies
2. Customer selects a movie
3. Customer selects a seat
4. System processes payment
5. Ticket is saved in the repository

Optional:

* Apply Discount

---

# Technologies Used

* UML
* Repository Pattern
* Object Oriented Programming
* C#
* GitHub
