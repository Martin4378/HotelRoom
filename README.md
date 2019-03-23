# HotelRoom

import  java.util.Scanner;

public class P42_HotelRoom {

    public static void main(String[] args) {
        Scanner console = new Scanner(System.in);
        String month = console.nextLine();
        int nights = Integer.parseInt(console.nextLine());
        double priceStudio = 0;
        double priceApartment = 0;

        if (month.equalsIgnoreCase("May") || month.equalsIgnoreCase("October")){
            priceApartment = nights * 65.00;
            priceStudio = nights * 50.00;
            if (nights > 7 && nights <= 14) {
                priceStudio = priceStudio - priceStudio * 0.05;
            } else if (nights > 14){
                priceStudio = priceStudio - priceStudio * 0.30;
            }
        } else if (month.equalsIgnoreCase("June") || month.equalsIgnoreCase("September")){
            priceApartment = nights * 68.70;
            priceStudio = nights * 75.20;
            if (nights > 14){
                priceStudio = priceStudio - priceStudio * 0.20;
            }
        } else if (month.equalsIgnoreCase("July") || month.equalsIgnoreCase("August")){
            priceApartment = nights * 77.00;
            priceStudio = nights * 76.00;
        } else {
            System.out.print("unknown");
            return;
        }
        if (nights > 14){
            priceApartment = priceApartment - priceApartment * 0.10;
        }
        System.out.printf("Apartment: %.2f lv.\n", priceApartment);
        System.out.printf("Studio: %.2f lv.", priceStudio);
    }

}
