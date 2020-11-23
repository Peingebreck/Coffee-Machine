package machine;

import java.util.*;

public class CoffeeMachine {
    static Scanner sc = new Scanner(System.in);
    static int water = 400;
    static int milk = 540;
    static int coffee = 120;
    static int cups = 9;
    static int money = 550;

    static Coffee espresso = new Coffee(250, 16, 0, 4);
    static Coffee latte = new Coffee(350, 20, 75, 7);
    static Coffee cappuccino = new Coffee(200, 12, 100, 6);

    public static void main(String[] args) {
            while (true) {
            System.out.println("Write action (buy, fill, take, remaining, exit):");
            String action = sc.next();
            if ("buy".equals(action)) {
                buyCoffee();
            } else if ("fill".equals(action)) {
                fillCoffeeMachine();
            } else if ("take".equals(action)) {
                takeMoney();
            } else if ("remaining".equals(action)) {
                printCoffeeMachineState();
            } else if ("exit".equals(action)) {
                break;
            } else {
                System.out.println("Unknown command");
            }
        }
    }
    public static void buyCoffee() {
        System.out.println("What do you want to buy? 1 - espresso, 2 - latte, 3 - cappuccino, back - to main menu:");
        String choice = sc.next();
        switch (choice) {
            case "1":
                calculateResources(espresso);
                break;
            case "2":
               calculateResources(latte);
                break;
            case "3":
                calculateResources(cappuccino);
                break;
            case "back":
                break;
            default:
                System.out.println("Unknown command");
                break;
        }
    }

    public static void fillCoffeeMachine() {
        System.out.println("Write how many ml of water do you want to add:");
        water += sc.nextInt();
        System.out.println("Write how many ml of milk do you want to add:");
        milk += sc.nextInt();
        System.out.println("Write how many grams of coffee beans do you want to add:");
        coffee += sc.nextInt();
        System.out.println("Write how many disposable cups of coffee do you want to add:");
        cups += sc.nextInt();
        System.out.println();
    }

    public static void takeMoney() {
        System.out.println("I gave you $" + money + '\r' + '\n');
        money = 0;
    }

    public static void printCoffeeMachineState(){
        System.out.println("The coffee machine has:");
        System.out.println(water + " of water");
        System.out.println(milk + " of milk");
        System.out.println(coffee +  " of coffee beans");
        System.out.println(cups +  " of disposable cups");
        System.out.println("$" + money +  " of money" + '\r' + '\n');
    }
    public static void calculateResources(Coffee typeOfCoffee) {
        ArrayList<String> resources = new ArrayList<>();
        String notEnough = "";
        if (water - typeOfCoffee.getWater() < 0) {
            resources.add("water");
        }
        if (coffee - typeOfCoffee.getCoffee() < 0) {
            resources.add("coffee");
        }
        if (milk - typeOfCoffee.getMilk() < 0) {
            resources.add("milk");
        }
        if (cups - 1 < 0) {
            resources.add("cups");
        }

        if (resources.size() == 1) {
            notEnough = resources.get(0);
        } else if (resources.size() == 2) {
            notEnough = resources.get(0) + " and " + resources.get(1);
        } else if (resources.size() == 3) {
            notEnough = resources.get(0) + ", " + resources.get(1) + " and " + resources.get(2);
        } else if (resources.size() == 4) {
            notEnough = resources.get(0) + ", " + resources.get(1) + ", " + resources.get(2) + " and " + resources.get(3);
        }

        if (resources.size() == 0){
            System.out.println("I have enough resources, making you a coffee!" + '\r' + '\n');
            water -= typeOfCoffee.getWater();
            milk -= typeOfCoffee.getMilk();
            coffee -= typeOfCoffee.getCoffee();
            cups --;
            money += typeOfCoffee.getCost();
        } else {
            System.out.println("Sorry, not enough " + notEnough + "!" + '\r' + '\n');
        }
    }
}

class Coffee {
    private final int water;
    private final int coffee;
    private final int milk;
    private final int cost;

    public Coffee (int water, int coffee, int milk, int cost) {
        this.water = water;
        this.coffee = coffee;
        this.milk = milk;
        this.cost = cost;
    }

    public int getWater() {
        return water;
    }

    public int getCoffee() {
        return coffee;
    }

    public int getMilk() {
        return milk;
    }

    public int getCost() {
        return cost;
    }
}



