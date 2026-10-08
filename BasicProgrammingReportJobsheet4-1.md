[Markdown_R25.md](https://github.com/user-attachments/files/33213679/Markdown_R25.md)
# JOBSHEET 4 - SELECTION 1

## Student Identity

- **Name:** Raul Ibrahim Hernov
- **NIM:** 264107020258
- **Study Program:** D-IV Informatics Engineering
- **Class:** TI_1I

---

## 1. OBJECTIVE

The practical work in this chapter focuses on selection structures in Java, including `IF`, `IF-ELSE`, `SWITCH-CASE`, and the ternary operator.

---

## 2. LABS & ACTIVITIES

### 2.1 Experiment 1: Using IF and IF-ELSE to Print the KRS

At the beginning of every semester, students must print their KRS (Study Plan Card) so it can be signed by their Academic Advisor (DPA). SIAKAD will check the student's UKT (tuition fee) payment status. If the student has fully paid the UKT, the system shows the KRS so it can be printed.

#### 2.1.1 Program Code Java

```java
package Week5;
import java.util.Scanner;

public class SelectionIfR25 {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        
        System.out.println("--- Print KRS SIAKAD --- ");
        System.out.print("Has Your UKT Been Paid? (true/false): ");
        boolean uktPaid = input.nextBoolean();
        
        if(uktPaid) {
            System.out.println("UKT Payment Verified.");
            System.out.println("Please Print Your KRS and Ask to Your DPA to Sign It");
        }
        input.close();
    }
}
```

#### 2.1.2 Execution Result / Screenshot Output

```text
--- Print KRS SIAKAD ---
Has Your UKT Been Paid? (true/false)
true
UKT Payment Verified.
Please Print Your KRS and Ask to Your DPA to Sign It
```

The program is run to display the KRS according to the UKT payment status.

#### 2.1.3 Answers to Questions / Reflection Questions

**Question 1: What value must you enter so that both lines inside the IF block are printed? Explain why only that value is accepted!**

**Answer:** `True`, because those two blocks are inside the IF statement. If I enter `False`, those two blocks in the IF statement will not be printed.

**Question 2: Run the program, then enter `false`. Which lines are printed and which lines are not? Explain the execution flow when the IF condition is false!**

**Answer:** The lines in IF are not printed because the IF statement only runs its code when the condition is true.

**Question 3: Run the program, then enter `TRUE` in capital letters and `yes`. What happens with each input? If the program stops with an error, explain the cause!**

```text
yes
Exception in thread "main" java.util.InputMismatchException
	at java.base/java.util.Scanner.throwFor(Scanner.java:977)
	at java.base/java.util.Scanner.next(Scanner.java:1632)
	at java.base/java.util.Scanner.nextBoolean(Scanner.java:1932)
	at Week5.SelectionIf12.main(SelectionIf12.java:10)
```

**Answer:** If we enter `TRUE`, the program will run clearly. If we enter `yes`, the program will display an error.

**Question 4: Modify the program by adding an ELSE structure so that when the user enters `false`, the output is `Registration rejected. Please pay your UKT first`.**

```java
package Week5;
import java.util.Scanner;

public class SelectionIf25 {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        
        System.out.println("--- Print KRS SIAKAD --- ");
        System.out.print("Has Your UKT Been Paid? (true/false): ");
        boolean uktPaid = input.nextBoolean();
        
        if (uktPaid) {
            System.out.println("UKT Payment Verified.");
            System.out.println("Please Print Your KRS and Ask to Your DPA to Sign It");
        } else {
            System.out.println("Registration rejected. Please pay your UKT first");
        }
        
        input.close();
    }
}
```


The program is modified with an ELSE statement and tested using both `true` and `false`.

### The result when the input is true:
```text
--- Print KRS SIAKAD --- 
Has Your UKT Been Paid? (true/false)
TRUE
UKT Payment Verified.
Please Print Your KRS and Ask to Your DPA to Sign It
```

### The result when the input is false:
```text
--- Print KRS SIAKAD --- 
Has Your UKT Been Paid? (true/false)
false
Registration rejected. Please pay your UKT first
```
---

### 2.2 Experiment 2: SWITCH-CASE to Print the KRS

The SIAKAD system checks the student's current semester, then shows the KRS for that semester so it can be printed.

#### 2.2.1 Program Code Java

```java
package Week5;
import java.util.Scanner;

public class SelectionSwitchR25 {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        System.out.println("--- Print KRS SIAKAD --- ");
        System.out.print("Enter Your Current Semester: ");

        int semester = input.nextInt();

        switch(semester) {
            case 1:
                System.out.println("KRS for Semester 1 is Displayed");
                break;
            case 2:
                System.out.println("KRS for Semester 2 is Displayed");
                break;
            case 3:
                System.out.println("KRS for Semester 3 is Displayed");
                break;
            case 4:
                System.out.println("KRS for Semester 4 is Displayed");
                break;
            case 5:
                System.out.println("KRS for Semester 5 is Displayed");
                break;
            case 6:
                System.out.println("KRS for Semester 6 is Displayed");
                break;
            case 7:
                System.out.println("KRS for Semester 7 is Displayed");
                break;
            case 8:
                System.out.println("KRS for Semester 8 is Displayed");
                break;
            default:
                System.out.println("Invalid semester entered.");
        }
        input.close();
    }
}
```

#### 2.2.2 Execution Result / Screenshot Output

The program is compiled and run using the semester input.

#### 2.2.3 Answers to Questions / Reflection Questions

**Question 1: Delete the `break;` statement in case 5, then compile and run the program again with the input 5. Explain the function of `break` in SWITCH-CASE!**

**Answer:** The output will display semester 5 & 6.

The function of `break` in the switch-case is to stop the progress when entering the specific statement. The remaining cases will be stopped, so it only displays the specific statement.

**Question 2: Run the program with the input 10, then with the input 0. What is the output? Explain the role of `default`.**

**Answer:** `Invalid semester`, because 10 and 0 are not in the program cases and do not match any value, so the program processes the `default` case. The role of `default` is to provide a block of code that runs when no case matches the value in the switch statement.

**Question 3: Change the data type of the semester variable to `double`, then compile the program. Does it compile successfully? List the data types that can be used as the expression in a switch!**

**Answer:** The program will produce an error and display an error message:

```text
Case constants in a switch on 'double' must have type 'double'
```

Data types that can be used as the expression in a switch are:

- `int`
- `byte`
- `char`
- `String`
- `short`

**Question 4: Convert the KRS printing program that uses SWITCH-CASE into an IF-ELSE IF-ELSE form. Which one is easier to read for this case, and why?**

**Answer:** In my opinion, Switch-Case is easier to read in this case because it is more organized and easier to read when handling multiple exact semester numbers.

---

## 3. ASSIGNMENT

The following tasks are performed in this Jobsheet:

1. Convert the IF-ELSE selection structure into a Ternary Operator.
2. Implement the given KRS validation flowchart using IF-ELSE.
3. Implement the Parking System using IF-ELSE.
4. Implement the Academic Queue Machine using SWITCH-CASE with a `default` case.

### 3.1 Assignment 1: Ternary Operator

#### 3.1.1 Program Code Java

```java
package Week5;

import java.util.Scanner;

public class TernaryOperatorR25 {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        System.out.println("--- Print KRS SIAKAD --- ");
        System.out.println("Has Your UKT Been Paid? (true/false)");
        boolean uktPaid = input.nextBoolean();

        String message = (uktPaid)
                ? "UKT Payment Verified. Please Print Your KRS and Ask to Your DPA to Sign It"
                : "Registration rejected. Please pay your UKT first";

        System.out.println(message);

        input.close();
    }
}
```

#### 3.1.2 Execution Result / Screenshot Output

The result is displayed for both `true` and `false` inputs.

#### 3.1.3 Reflection

**Answer:** In my opinion, the Ternary Operator is better used for short, simple decisions that return a value. Otherwise, `if-else` should be used when the logic becomes more complex.

---

### 3.2 Assignment 2: KRS SKS Validation

A KRS system validates the number of credits (SKS) taken by a student, where the maximum number allowed is 24 credits.

#### 3.2.1 Program Code Java

```java
package Week5;
import java.util.Scanner;

public class Assignment2SelectionAttendanceNo {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        
        System.out.println("--- KRS SKS Validation ---");
        System.out.print("Enter the number of SKS you want to take: ");
        int sks = input.nextInt();
        
        // Validasi SKS maksimal 24
        if (sks > 24) {
            System.out.println("Validation failed: Maximum allowed SKS is 24 credits.");
        } else if (sks > 0) {
            System.out.println("Validation success: You are taking " + sks + " credits.");
        } else {
            System.out.println("Validation failed: Invalid SKS amount.");
        }
        
        input.close();
    }
}
```

#### 3.2.2 Execution Result / Screenshot Output

The program result is displayed according to the number of SKS entered.

---

### 3.3 Assignment 3A: Parking System

#### 3.3.1 Program Code Java

```java
package Week5;
import java.util.Scanner;

public class AssignmentParkingAttendanceNo {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        
        System.out.println("--- Parking System ---");
        System.out.print("Enter vehicle type (1 for Car, 2 for Motorcycle): ");
        int vehicleType = input.nextInt();
        
        System.out.print("Enter parking duration (in hours): ");
        int hours = input.nextInt();
        
        int totalFee = 0;
        
        // Menghitung tarif menggunakan IF-ELSE
        if (vehicleType == 1) {
            totalFee = hours * 5000;
            System.out.println("Vehicle: Car");
            System.out.println("Total Parking Fee: Rp " + totalFee);
        } else if (vehicleType == 2) {
            totalFee = hours * 2000;
            System.out.println("Vehicle: Motorcycle");
            System.out.println("Total Parking Fee: Rp " + totalFee);
        } else {
            System.out.println("Invalid vehicle type entered.");
        }
        
        input.close();
    }
}
```

#### 3.3.2 Execution Result / Screenshot Output

The program displays the parking result according to the entered data.

---

### 3.4 Assignment 3B: Academic Queue Machine

#### 3.4.1 Program Code Java

```java
package Week5;
import java.util.Scanner;

public class AssignmentQueueAttendanceNo {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        
        System.out.println("--- Academic Queue Machine ---");
        System.out.println("1. Academic Affairs");
        System.out.println("2. Student Affairs");
        System.out.println("3. Finance & Payment");
        System.out.println("4. IT Support");
        System.out.print("Enter your selected service code (1-4): ");
        
        int serviceCode = input.nextInt();
        
        switch(serviceCode) {
            case 1:
                System.out.println("Queue for Academic Affairs. Please wait.");
                break;
            case 2:
                System.out.println("Queue for Student Affairs. Please wait.");
                break;
            case 3:
                System.out.println("Queue for Finance & Payment. Please wait.");
                break;
            case 4:
                System.out.println("Queue for IT Support. Please wait.");
                break;
            default:
                // Pesan default sesuai dengan instruksi pada dokumen
                System.out.println("Service code is not available");
                break;
        }
        
        input.close();
    }
}
```

The program includes a `default` case to handle codes outside 1–4 with the message:

```text
Service code is not available
```

#### 3.4.2 Execution Result / Screenshot Output

The program displays the queue service according to the selected service code.

---

## 4. CONCLUSION

The practical work demonstrates how selection structures can be used to make decisions in Java programs. `IF`, `IF-ELSE`, `IF-ELSE IF-ELSE`, `SWITCH-CASE`, and the Ternary Operator each have different uses depending on the complexity and form of the decision.

`IF-ELSE` is useful for conditional logic, while `SWITCH-CASE` is easier to organize when handling multiple exact values. The Ternary Operator is suitable for short and simple decisions that return a value.

---
