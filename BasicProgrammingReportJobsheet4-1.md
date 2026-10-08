[BasicProgrammingReportJobsheet4-1.md](https://github.com/user-attachments/files/33215180/BasicProgrammingReportJobsheet4-1.md)
# BASIC PROGRAMMING PRACTICUM REPORT

**MEETING-5: Selection**

**JOBSHEET 4**

## Student Identity

- **Name:** Raul Ibrahim Hernov
- **NIM:** 264107020258
- **Study Program:** D-IV Informatics Engineering
- **Class:** TI_1I

**INFORMATION TECHNOLOGY DEPARTMENT**
**STATE POLYTECHNIC OF MALANG**
**2026/2027**

---

## 1. OBJECTIVE

The practical work in this chapter focuses on selection structures in Java, including `IF`, `IF-ELSE`, `IF-ELSE IF-ELSE`, `SWITCH-CASE`, and the ternary operator.

---

## 2. LABS & ACTIVITIES

### 2.1 Experiment 1: Using IF and IF-ELSE to Print the KRS

At the beginning of every semester, students must print their KRS (Study Plan Card) so it can be signed by their Academic Advisor (DPA). SIAKAD will check the student's UKT (tuition fee) payment status. If the student has fully paid the UKT, the system shows the KRS so it can be printed.

#### 2.1.1 Program Code (`SelectionIf25.java`, IF only)

```java
package Week5;
import java.util.Scanner;

public class SelectionIf25 {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        System.out.println("--- Print KRS SIAKAD ---");
        System.out.println("Has Your UKT Been Paid? (true/false)");
        boolean uktPaid = input.nextBoolean();

        if (uktPaid) {
            System.out.println("UKT Payment Verified.");
            System.out.println("Please Print Your KRS and Ask to Your DPA to Sign It");
        }
        input.close();
    }
}
```

#### 2.1.2 Execution Result

```
--- Print KRS SIAKAD ---
Has Your UKT Been Paid? (true/false)
true
UKT Payment Verified.
Please Print Your KRS and Ask to Your DPA to Sign It
```

#### 2.1.3 Answers to Questions

**Question 1: What value must you enter so that both lines inside the IF block are printed? Explain why only that value is accepted!**

**Answer:** The value that must be entered is `true`. The IF statement runs the lines inside its block only when the condition evaluates to `true`. The variable `uktPaid` is a `boolean`, and the condition `if (uktPaid)` is satisfied only when `uktPaid` holds `true`. If `false` is entered, the condition is not satisfied and both lines inside the block are skipped.

**Question 2: Run the program, then enter `false`. Which lines are printed and which lines are not? Explain the execution flow when the IF condition is false!**

**Answer:** The header lines (`--- Print KRS SIAKAD ---` and the question prompt) are still printed because they are outside the IF block. The two lines inside the IF block ("UKT Payment Verified." and "Please Print Your KRS and Ask to Your DPA to Sign It") are **not** printed. The flow is: the program reads `false`, evaluates the condition `uktPaid`, finds it is false, skips the whole IF block, and continues to the next statement after the block (`input.close()`), and then the program ends with no further output.

**Question 3: Run the program, then enter `TRUE` in capital letters and `yes`. What happens with each input? If the program stops with an error, explain the cause!**

**Answer:**

- `TRUE`: the program runs normally and prints the two lines of the IF block. `Scanner.nextBoolean()` is not case-sensitive, so `TRUE`, `True`, and `true` are all read as the boolean value `true`.
- `yes`: the program stops with an error because `nextBoolean()` only accepts the words `true` or `false` (in any letter case). Any other input cannot be converted to a boolean, so Java throws `InputMismatchException`.

```
--- Print KRS SIAKAD ---
Has Your UKT Been Paid? (true/false)
yes
Exception in thread "main" java.util.InputMismatchException
	at java.base/java.util.Scanner.throwFor(Scanner.java:947)
	at java.base/java.util.Scanner.next(Scanner.java:1602)
	at java.base/java.util.Scanner.nextBoolean(Scanner.java:1902)
	at Week5.SelectionIf25.main(SelectionIf25.java:10)
```

**Question 4: Modify the program by adding an ELSE structure so that when the user enters `false`, the output is "Registration rejected. Please pay your UKT first".**

```java
package Week5;
import java.util.Scanner;

public class SelectionIf25 {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        System.out.println("--- Print KRS SIAKAD ---");
        System.out.println("Has Your UKT Been Paid? (true/false)");
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

The result when the input is `true`:

```
--- Print KRS SIAKAD ---
Has Your UKT Been Paid? (true/false)
true
UKT Payment Verified.
Please Print Your KRS and Ask to Your DPA to Sign It
```

The result when the input is `false`:

```
--- Print KRS SIAKAD ---
Has Your UKT Been Paid? (true/false)
false
Registration rejected. Please pay your UKT first
```

---

### 2.2 Experiment 2: SWITCH-CASE to Print the KRS

The SIAKAD system checks the student's current semester, then shows the KRS for that semester so it can be printed.

#### 2.2.1 Program Code (`SelectionSwitch25.java`)

```java
package Week5;
import java.util.Scanner;

public class SelectionSwitch25 {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        System.out.println("--- Print KRS SIAKAD ---");
        System.out.println("Enter Your Current Semester: ");
        int semester = input.nextInt();

        switch (semester) {
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

#### 2.2.2 Execution Result

```
--- Print KRS SIAKAD ---
Enter Your Current Semester:
6
KRS for Semester 6 is Displayed
```

#### 2.2.3 Answers to Questions

**Question 1: Delete the `break;` statement in case 5, then compile and run the program again with the input 5. Write down the output, then explain the function of `break`.**

**Answer:** Output with input `5` (without `break` in case 5):

```
--- Print KRS SIAKAD ---
Enter Your Current Semester:
5
KRS for Semester 5 is Displayed
KRS for Semester 6 is Displayed
```

Without `break`, the program continues running the statements of the next case (case 6) even though the value does not match it. This behavior is called *fall-through*. It stops only when a `break` is reached or the switch ends. So the function of `break` is to terminate the switch block after the matching case has finished, so that the following cases are not executed. (The code was restored to its original form afterwards.)

**Question 2: Run the program with the input 10, then with the input 0. What is the output? Explain the role of `default` and what happens if `default` is deleted.**

**Answer:** For both inputs the output is:

```
Invalid semester entered.
```

The values 10 and 0 do not match any `case` (1 to 8), so the program runs the `default` block. The role of `default` is to handle every value that does not match any case, such as invalid input. If `default` is deleted, the program still compiles and runs, but for input 10 or 0 nothing is printed after the input, so the user gets no feedback that the input is invalid.

**Question 3: Change the data type of the semester variable to `double`, then compile the program. Does it compile successfully? Write down the error message and explain its cause. List the data types that can be used as the expression in a switch.**

**Answer:** No, the program fails to compile. The error message shown by the IDE:

```
Case constants in a switch on 'double' must have type 'double'
```

(The exact wording depends on the compiler/IDE version.) The cause is that a `switch` expression does not support `double`: floating-point values are not exact, so they cannot be reliably matched against constants like `case 1:`. Data types that can be used as the expression in a switch:

- `byte`
- `short`
- `char`
- `int`
- their wrapper classes (`Byte`, `Short`, `Character`, `Integer`)
- `String`
- `enum`

Not allowed: `long`, `float`, `double`, and `boolean`.

**Question 4: Create `SelectionIfElse25.java`. Convert the program into an IF - ELSE IF - ELSE form with exactly the same output. Which one is easier to read, and why?**

```java
package Week5;
import java.util.Scanner;

public class SelectionIfElse25 {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        System.out.println("--- Print KRS SIAKAD ---");
        System.out.println("Enter Your Current Semester: ");
        int semester = input.nextInt();

        if (semester == 1) {
            System.out.println("KRS for Semester 1 is Displayed");
        } else if (semester == 2) {
            System.out.println("KRS for Semester 2 is Displayed");
        } else if (semester == 3) {
            System.out.println("KRS for Semester 3 is Displayed");
        } else if (semester == 4) {
            System.out.println("KRS for Semester 4 is Displayed");
        } else if (semester == 5) {
            System.out.println("KRS for Semester 5 is Displayed");
        } else if (semester == 6) {
            System.out.println("KRS for Semester 6 is Displayed");
        } else if (semester == 7) {
            System.out.println("KRS for Semester 7 is Displayed");
        } else if (semester == 8) {
            System.out.println("KRS for Semester 8 is Displayed");
        } else {
            System.out.println("Invalid semester entered.");
        }
        input.close();
    }
}
```

The output (valid input `5`):

```
--- Print KRS SIAKAD ---
Enter Your Current Semester:
5
KRS for Semester 5 is Displayed
```

The output when the input is invalid (`10`):

```
--- Print KRS SIAKAD ---
Enter Your Current Semester:
10
Invalid semester entered.
```

**Answer:** In my opinion, SWITCH-CASE is easier to read for this case because every semester is compared against one variable using exact values. Each `case` is a clear, separate line, while IF-ELSE IF repeats the condition `semester == ...` every time, which makes the code longer.

---

## 3. ASSIGNMENT

### 3.1 Assignment 1: Ternary Operator (`Assignment1Selection25.java`)

#### 3.1.1 Program Code

```java
package Week5;
import java.util.Scanner;

public class Assignment1Selection25 {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        System.out.println("--- Print KRS SIAKAD ---");
        System.out.println("Has Your UKT Been Paid? (true/false)");
        boolean uktPaid = input.nextBoolean();

        String message = uktPaid
                ? "UKT Payment Verified.\nPlease Print Your KRS and Ask to Your DPA to Sign It"
                : "Registration rejected. Please pay your UKT first";

        System.out.println(message);
        input.close();
    }
}
```

#### 3.1.2 Execution Result

Input `true`:

```
--- Print KRS SIAKAD ---
Has Your UKT Been Paid? (true/false)
true
UKT Payment Verified.
Please Print Your KRS and Ask to Your DPA to Sign It
```

Input `false`:

```
--- Print KRS SIAKAD ---
Has Your UKT Been Paid? (true/false)
false
Registration rejected. Please pay your UKT first
```

#### 3.1.3 Reflection

**Answer:** The ternary operator is better used for short, simple decisions with two outcomes that only need to produce a value, such as assigning one of two messages to a variable. It should not be used when the logic is complex, has many branches, needs several statements per branch, or is nested, because it becomes hard to read. In those cases `if-else` is better.

---

### 3.2 Assignment 2: KRS SKS Validation (`Assignment2Selection25.java`)

A KRS system validates the number of credits (SKS) taken by a student, where the maximum allowed is 24 credits. The program follows the given flowchart: if `totalCredits > 24` it prints "Exceeds the limit", otherwise it prints "KRS is valid".

#### 3.2.1 Program Code

```java
package Week5;
import java.util.Scanner;

public class Assignment2Selection25 {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        System.out.println("Enter total credits (SKS): ");
        int totalCredits = input.nextInt();

        if (totalCredits > 24) {
            System.out.println("Exceeds the limit");
        } else {
            System.out.println("KRS is valid");
        }
        input.close();
    }
}
```

#### 3.2.2 Execution Result

Input `20`:

```
Enter total credits (SKS):
20
KRS is valid
```

Input `30`:

```
Enter total credits (SKS):
30
Exceeds the limit
```

---

### 3.3 Assignment 3A: Parking System (`AssignmentParking25.java`)

Paid parking for two-wheeled vehicles: the fee is Rp 2,000 for the first 2 hours, then Rp 1,000 for each additional hour.

#### 3.3.1 Program Code

```java
package Week5;
import java.util.Scanner;

public class AssignmentParking25 {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        System.out.println("--- Paid Parking System for Two-Wheeled Vehicles ---");
        System.out.println("Enter Parking Duration (hours): ");
        int parkingDuration = input.nextInt();
        int parkingFee = 2000;

        if (parkingDuration <= 2) {
            System.out.println("Parking Fee: Rp. " + parkingFee);
        } else {
            System.out.println("Parking Fee: Rp. " + (parkingFee + (parkingDuration - 2) * 1000));
        }
        input.close();
    }
}
```

#### 3.3.2 Execution Result

Input `2`:

```
--- Paid Parking System for Two-Wheeled Vehicles ---
Enter Parking Duration (hours):
2
Parking Fee: Rp. 2000
```

Input `5`:

```
--- Paid Parking System for Two-Wheeled Vehicles ---
Enter Parking Duration (hours):
5
Parking Fee: Rp. 5000
```

---

### 3.4 Assignment 3B: Academic Queue Machine (`AssignmentQueue25.java`)

#### 3.4.1 Program Code

```java
package Week5;
import java.util.Scanner;

public class AssignmentQueue25 {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        System.out.println("State Polytechnic of Malang Student Services");
        System.out.println("Enter Your Service Code: ");
        int serviceCode = input.nextInt();

        switch (serviceCode) {
            case 1:
                System.out.println("Legalization of Diploma");
                System.out.println("The Location is on Counter A");
                break;
            case 2:
                System.out.println("Certificate of Active Student Status");
                System.out.println("The Location is on Counter B");
                break;
            case 3:
                System.out.println("UKT Payment");
                System.out.println("The Location is on Counter C");
                break;
            case 4:
                System.out.println("Application for Academic Leave");
                System.out.println("The Location is on Counter D");
                break;
            default:
                System.out.println("Service code is not available");
        }
        input.close();
    }
}
```

#### 3.4.2 Execution Result

Input `3`:

```
State Polytechnic of Malang Student Services
Enter Your Service Code:
3
UKT Payment
The Location is on Counter C
```

Input `7` (outside 1-4):

```
State Polytechnic of Malang Student Services
Enter Your Service Code:
7
Service code is not available
```

---

## 4. CONCLUSION

The practical work demonstrates how selection structures are used to make decisions in Java programs. `IF` runs a block only when its condition is true, `IF-ELSE` adds an alternative path, and `IF-ELSE IF-ELSE` handles several conditions in order. `SWITCH-CASE` is easier to organize when comparing one variable against many exact values, but it needs `break` to prevent fall-through and `default` to handle unmatched values. The ternary operator is suitable for short, simple decisions that return a value.
