class Lamp {
    // 1. CLASS: Defines the structure (data fields) that ALL Lamp objects will have.
    String color;
    boolean isOn;

    // CLASS: Defines the behavior (methods) that ALL Lamp objects will share.
    public Lamp(String color) {
        this.color = color;
        this.isOn = false;
        // This constructor is part of the class definition (the blueprint)
    }

    public void switchOn() {
        if (!isOn) {
            isOn = true;
            System.out.println("-> " + color + " lamp switched ON.");
        }
    }

    public void switchOff() {
        if (isOn) {
            isOn = false;
            System.out.println("-> " + color + " lamp switched OFF.");
        }
    }
}

public class DifferenceDemo {
    public static void main(String[] args) {
        System.out.println("--- Demonstrating Objects and Classes ---");
        
        // 2. OBJECTS: Creating concrete instances (objects) from the class (blueprint)

        // Object 1: A specific instance named 'deskLamp'.
        // This step allocates memory for a new Lamp object based on the Lamp class.
        Lamp deskLamp = new Lamp("Silver"); 
        
        // Object 2: A separate, distinct instance named 'floorLamp'.
        // This object has its own memory space and state (color, isOn).
        Lamp floorLamp = new Lamp("Wood Grain");

        
        System.out.println("\n[Action 1] Desk Lamp actions:");
        deskLamp.switchOn(); 
        deskLamp.switchOff(); 
        
        // The objects maintain separate, unique states (data):
        System.out.println("\n[Action 2] Floor Lamp actions:");
        floorLamp.switchOn(); 
        
        System.out.println("\n[Action 3] Checking current states:");
        // Both objects share the same *behavior* (toString/isOn logic) defined by the *class* (Lamp),
        // but their *states* (data) are unique to each *object*.
        System.out.println("-> Desk Lamp state (Silver): " + (deskLamp.isOn ? "ON" : "OFF"));
        System.out.println("-> Floor Lamp state (Wood Grain): " + (floorLamp.isOn ? "ON" : "OFF"));
    }
}
