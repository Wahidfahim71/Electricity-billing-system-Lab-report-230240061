# Electricity-billing-system-Lab-report-230240061

Program:

Import java.util.Scanner;

Public class ElectricityBillingSystem {

    Public static void main(String[] args) {

        Scanner scanner = new Scanner(System.in);



        // Customer class

        Class Customer {

            Private int customerId;

            Private String name;

            Private String address;



            Public Customer(int customerId, String name, String address) {

                This.customerId = customerId;

                This.name = name;

                This.address = address;

            }



            Public int getCustomerId() {

                Return customerId;

            }



            Public String getName() {

                Return name;

            }



            Public String getAddress() {

                Return address;

            }

        }



        // ElectricityBill class

        Class ElectricityBill {

            Private int billId;

            Private int customerId;

            Private double unitsConsumed;

            Private double totalAmount;



            Public ElectricityBill(int billId, int customerId, double unitsConsumed) {

                This.billId = billId;

                This.customerId = customerId;

                This.unitsConsumed = unitsConsumed;

                This.totalAmount = calculateTotalAmount(unitsConsumed);

            }



            Private double calculateTotalAmount(double unitsConsumed) {

                If (unitsConsumed <= 100) {

                    Return unitsConsumed * 0.10; // $0.10 per unit for 0-100 units

                } else if (unitsConsumed <= 200) {

                    Return 10 + ((unitsConsumed – 100) * 0.15); // $0.15 per unit for 101-200 units

                } else {

                    Return 25 + ((unitsConsumed – 200) * 0.20); // $0.20 per unit for 201+ units

                }

            }



            Public int getBillId() {

                Return billId;

            }



            Public int getCustomerId() {

                Return customerId;

            }



            Public double getUnitsConsumed() {

                Return unitsConsumed;

            }



            Public double getTotalAmount() {

                Return totalAmount;

            }

        }



        // Get customer details from user input

        System.out.println(“Enter customer ID:”);

        Int customerId = scanner.nextInt();

        Scanner.nextLine(); // Consume the newline character

        System.out.println(“Enter customer name:”);

        String name = scanner.nextLine();

        System.out.println(“Enter customer address:”);

        String address = scanner.nextLine();



        // Get electricity usage details from user input

        System.out.println(“Enter units consumed:”);

        Double unitsConsumed = scanner.nextDouble();



        // Create customer and electricity bill objects

        Customer customer = new Customer(customerId, name, address);

        ElectricityBill bill = new ElectricityBill(1, customerId, unitsConsumed);

        // Display customer information and bill details

        System.out.println(“\nCustomer Information:”);

        System.out.println(“ID: “ + customer.getCustomerId());

        System.out.println(“Name: “ + customer.getName());

        System.out.println(“Address: “ + customer.getAddress());



        System.out.println(“\nElectricity Bill Details:”);

        System.out.println(“Units Consumed: “ + bill.getUnitsConsumed());

        System.out.println(“Total Amount: $” + bill.getTotalAmount());



        Scanner.close();

    }

}
