# Company Car Rental System

This project implements a company system for managing car rentals. It uses a linked list to represent the rentals and provides various functionalities for managing and querying rental data.

## Overview

The system is implemented using two primary classes: `RentNode` and `Company`.

### RentNode
`RentNode` represents a single rental entry in the company’s rental list. Each rental is stored in a node that points to the next rental in the list.

### Company
The `Company` class manages a linked list of rental records. The rental records are ordered by the pickup date, and if there are multiple rentals with the same pickup date, the one with the longest duration comes first.

## Class Details

### RentNode

The `RentNode` class has the following attributes and methods:

#### Attributes:
1. **rent**: An object of type `Rent` representing the rental information.
2. **next**: A pointer to the next `RentNode` in the list.

#### Constructors:
1. `RentNode(Rent r)`: Creates a new node with the given `Rent` object and sets the `next` pointer to `null`.
2. `RentNode(Rent r, RentNode next)`: Creates a new node with the given `Rent` object and a pointer to the next node.
3. `RentNode(RentNode other)`: A copy constructor that creates a new `RentNode` by copying the data from another node.

#### Methods:
1. `getRent()`: Returns the rental object stored in this node.
2. `getNext()`: Returns the pointer to the next node in the list.
3. `setRent(Rent r)`: Updates the rental object stored in the node.
4. `setNext(RentNode next)`: Updates the pointer to the next node.

### Company

The `Company` class manages a list of rental records using the `RentNode` class. It has the following methods:

#### Methods:
1. `addRent(String name, Car car, Date pickDate, Date returnDate)`: Adds a rental record to the company’s list in the correct order (by pickup date and rental duration). Returns `true` if the rental was successfully added, and `false` if the rental already exists.
2. `removeRent(Date d)`: Removes the first rental that matches the specified return date. Returns `true` if a rental was removed, otherwise `false`.
3. `getNumOfRents()`: Returns the total number of rentals in the company.
4. `getSumOfPrices()`: Returns the total revenue from all rentals.
5. `getSumOfDays()`: Returns the total number of rental days across all rentals.
6. `averageRent()`: Returns the average rental duration. If there are no rentals, returns `0.0`.
7. `lastCarRent()`: Returns the car with the latest return date. If there are no rentals, returns `null`.
8. `longestRent()`: Returns the rental with the longest duration. If there are multiple rentals with the same duration, returns the first one. If there are no rentals, returns `null`.
9. `mostCommonRate()`: Returns the most common rental rating. If there is a tie, returns the higher rating. If there are no rentals, returns `'N'`.
10. `includes(List<Rent> rents)`: Checks if the given list of rentals is fully contained within the company’s rental list.
11. `merge(Company other)`: Merges two company rental lists while maintaining the order based on pickup date and rental duration.
12. `unifyRents()`: Removes duplicate rentals based on the rules defined in the `Rent` class and merges them into one.
13. `toString()`: Returns a string representation of all rentals in the company in the following format:

