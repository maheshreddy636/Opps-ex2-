# Opps-ex2-

a 

import java.util.Scanner;
import java.util.Random;

public class SimplePasswordGenerator {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        Random random = new Random();

        char[] small = {'a','b','c','d','e','f','g','h','i','j','k','l','m',
                        'n','o','p','q','r','s','t','u','v','w','x','y','z'};

        char[] capital = {'A','B','C','D','E','F','G','H','I','J','K','L','M',
                          'N','O','P','Q','R','S','T','U','V','W','X','Y','Z'};

        int[] numbers = {0,1,2,3,4,5,6,7,8,9};

        System.out.print("Enter the password length: ");
        int length = scanner.nextInt();

        if (length < 3) {
            System.out.println("Password must be at least 3 characters long.");
            return;
        }

        char[] password = new char[length];

        password[0] = small[random.nextInt(small.length)];
        password[1] = capital[random.nextInt(capital.length)];
        password[2] = (char)(numbers[random.nextInt(numbers.length)] + '0');

        for (int i = 3; i < length; i++) {
            int choice = random.nextInt(3);
            if (choice == 0) {
                password[i] = small[random.nextInt(small.length)];
            } else if (choice == 1) {
                password[i] = capital[random.nextInt(capital.length)];
            } else {
                password[i] = (char)(numbers[random.nextInt(numbers.length)] + '0');
            }
        }

        for (int i = 0; i < length; i++) {
            int j = random.nextInt(length);
            char temp = password[i];
            password[i] = password[j];
            password[j] = temp;
        }

        System.out.print("The Generated Password is: ");
        for (int i = 0; i < length; i++) {
            System.out.print(password[i]);
        }

        System.out.println();
    }
}




b 

import java.util.Scanner;

public class MultiplesOf9And3 {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int[] numbers = new int[10];
        int[] multiples = new int[10];
        int count = 0;

        System.out.println("Enter 10 numbers:");

        for (int i = 0; i < 10; i++) {
            numbers[i] = scanner.nextInt();
        }

        for (int i = 0; i < 10; i++) {
            if (numbers[i] % 9 == 0) {
                multiples[count] = numbers[i];
                count++;
            }
        }

        System.out.println("The numbers that are multiples of both 9 and 3:");
        for (int i = 0; i < count; i++) {
            if (i != count - 1) {
                System.out.print(multiples[i] + ",");
            } else {
                System.out.print(multiples[i]);
            }
        }

        System.out.println();
    }
}



