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

# Railway Reservation System

## Features
- Check seat availability
- Book tickets
- View reservation
- Cancel tickets

## How to run
1. Open main.py
2. Run using Python
3. Follow menu options
