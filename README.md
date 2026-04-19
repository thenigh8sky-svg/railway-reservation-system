print("Welcome to Railway Reservation System")
# railway-reservation-system
total_seats = 50
seats = list(range(1, total_seats + 1))
bookings = {}

import random

def check_availability():
    print(f"\nAvailable Seats: {len(seats)}")
    print("Seats:", seats)

def book_ticket():
    if not seats:
        print("No seats available!")
        return
    
    name = input("Enter Name: ")
    age = input("Enter Age: ")
    
    seat = seats.pop(0)
    booking_id = "B" + str(random.randint(1000, 9999))
    
    bookings[booking_id] = {
        "name": name,
        "age": age,
        "seat": seat
    }
    
    print(f"Booked Successfully! ID: {booking_id}, Seat: {seat}")

def view_ticket():
    bid = input("Enter Booking ID: ")
    if bid in bookings:
        print(bookings[bid])
    else:
        print("Booking not found")

def cancel_ticket():
    bid = input("Enter Booking ID: ")
    if bid in bookings:
        seats.append(bookings[bid]["seat"])
        del bookings[bid]
        print("Cancelled successfully")
    else:
        print("Booking not found")

while True:
    print("\n1.Check 2.Book 3.View 4.Cancel 5.Exit")
    choice = input("Enter choice: ")
    
    if choice == "1":
        check_availability()
    elif choice == "2":
        book_ticket()
    elif choice == "3":
        view_ticket()
    elif choice == "4":
        cancel_ticket()
    elif choice == "5":
        break
    else:
        print("Invalid choice")
