problem 1 
public class vehicle {
    protected String brand;
    protected String model;
    protected int Year;

    public vehicle(String brand, String model, int Year){
        this.brand = brand;
        this.model = model;
        this.Year = Year;
    }
    public void displayDetails() {
        System.out.println("Brand: " + brand);
        System.out.println("Model: " + model);
        System.out.println("Manufacturing Year: " + Year);
    }
    public double calculateRentalPrice(int days) {
        return days * 500;
    }
    public double calculateRentalPrice(int days, double discount) {
        double price = calculateRentalPrice(days);
        return price - (price * discount / 100);
    }
    public String toString() {
        return "Brand: " + brand + " Model: " + model + "Year: " + Year; 
    }
}
public class car extends vehicle {
    private int numberOfDoors;

    public car(String brand, String model, int year, int numberOfDoors) {
        super(brand, model, year);
        this.numberOfDoors = numberOfDoors;
    }
    public void displayDetails() {
        super.displayDetails();
        System.out.println("Number of Doors: " + numberOfDoors);
    }  
    public double calculateRentalPrice(int days) {
        return days * 700;
    }
    public String toString() {
        return super.toString() +" Engine Capacity: " + engineCapacity + " cc" ;
    }
}
public class Motorcycle extends vehicle {
    private int engineCapacity;

    public Motorcycle(String brand, String model, int year, int engineCapacity) {
        super(brand, model, year);
        this.engineCapacity = engineCapacity;
    }
    public void displayDetails() {
        super.displayDetails();
        System.out.println("Engine Capacity: " + engineCapacity + " cc");
    }
    public double calculateRentalPrice(int days) {
        return days * 300;
    }
    public String toString() {
        return super.toString() +" Engine Capacity: " + engineCapacity + " cc";
    
    }
}
public class main {
    public static void main(String[] args) {
     car c= new car("Toyota", "Corolla", 2023, 4);
        Motorcycle motorcycle =new Motorcycle("Honda", "CBR", 2022, 600);
        
        System.out.println("=== Car Details ===");
        c.displayDetails();
        System.out.println("\n=== Motorcycle Details ===");
        motorcycle.displayDetails();
        System.out.println("\n=== Rental Prices ===");
        System.out.println("Car rental for 3 days: "+ c.calculateRentalPrice(3));
        System.out.println("Motorcycle rental for 3 days: " + motorcycle.calculateRentalPrice(3));
        System.out.println("\n=== Overloaded Method ===");
        System.out.println("Car rental with 10% discount: "+ c.calculateRentalPrice(3, 10));
        System.out.println("Motorcycle rental with 10% discount: "+ c.calculateRentalPrice(3, 10));
        System.out.println("\n=== Objects ===");
        System.out.println(c);
        System.out.println(motorcycle);
    }
}
problem 2 
