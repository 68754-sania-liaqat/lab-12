# lab-12

PROGRAM :01
/*
 * Click nbfs://nbhost/SystemFileSystem/Templates/Licenses/license-default.txt to change this license
 */

package vehicle;

/**
 *
 * @author DELL
 */
abstract class Vehicle{
    abstract void start();
}

// Car class
class Car extends Vehicle {
    private String model;

    public Car(String model) {
        this.model = model;
    }

    @Override
    void start() {
        System.out.println("Car " + model + " is starting");
    }
}

// Motorcycle class
class Motorcycle extends Vehicle {
    private String brand;

    public Motorcycle(String brand) {
        this.brand = brand;
    }

    @Override
    void start() {
        System.out.println("Motorcycle " + brand + " is starting");
    }
}

// Main class
public class Main {
    public static void main(String[] args) {

        Car car = new Car("Toyota");
        Motorcycle motr = new Motorcycle("Honda");

        car.start();
        motr.start();
    }
}







PROGRAM:02
/*
 * Click nbfs://nbhost/SystemFileSystem/Templates/Licenses/license-default.txt to change this license
 */

package Seat;

/**
 *
 * @author DELL
// Abstract class
abstract class Seat {
    // Abstract method with exception
    abstract double calculateSeatPrice(int numberOfSeats) throws IllegalArgumentException;

    // Common validation (optional helper)
    protected void validateSeats(int numberOfSeats) {
        if (numberOfSeats <= 0) {
            throw new IllegalArgumentException("Number of seats must be positive!");
        }
    }
}

// Business Class
class BusinessClass extends Seat {

    @Override
    double calculateSeatPrice(int numberOfSeats) throws IllegalArgumentException {
        validateSeats(numberOfSeats);
        double pricePerSeat = 50000; // Example price
        return numberOfSeats * pricePerSeat;
    }
}

// First Class
class FirstClass extends Seat {

    @Override
    double calculateSeatPrice(int numberOfSeats) throws IllegalArgumentException {
        validateSeats(numberOfSeats);
        double pricePerSeat = 80000; // Example price
        return numberOfSeats * pricePerSeat;
    }
}

// Economy Class
class EconomyClass extends Seat {

    @Override
    double calculateSeatPrice(int numberOfSeats) throws IllegalArgumentException {
        validateSeats(numberOfSeats);
        double pricePerSeat = 20000; // Example price
        return numberOfSeats * pricePerSeat;
    }
}


// Main Class
public class AirlineTicketSystem {
    public static void main(String[] args) {

        // Creating objects
        Seat business = new BusinessClass();
        Seat first = new FirstClass();
        Seat economy = new EconomyClass();

        // Calculate prices
        try {
            System.out.println("Business Class Price: " + business.calculateSeatPrice(2));
            System.out.println("First Class Price: " + first.calculateSeatPrice(1));
            System.out.println("Economy Class Price: " + economy.calculateSeatPrice(3));

        } catch (IllegalArgumentException e) {
            System.out.println("Error: " + e.getMessage());
        }
    }
}

