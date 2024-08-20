---
created: 2024-08-13 13:04
tags: 
Parent Topic: 
Related Topics:
---
***
## What is Recursion?
Recursion is the process in which the function calls itself.

### Q1. Print the numbers 1 to 5 using recursion

```java
public class recursion1 {

    // Method to print numbers from 1 to n using recursion
    public void print(int n) {
        // Base case: If n is 0, stop the recursion
        if (n == 0) {
            return;
        }

        // Recursive call: Decrease n by 1 and call the method again
        print(n - 1);

        // After all recursive calls are done, print the current value of n
        System.out.print(n + " ");
    }

    public static void main(String[] args) {
        // Create an instance of the recursion1 class
        recursion1 r = new recursion1();

        // Call the print method with the value 5
        r.print(5); // This will print "1 2 3 4 5 "
    }
}

```
### Order of Execution

When you have a recursive function like this, the order of operations is important. Here's the sequence:

1. **Recursive Call First:**
    
    - The method calls itself recursively with a smaller value (`n - 1`).
    - Each recursive call continues to reduce `n` until it reaches the base case (`n == 0`).
2. **Execution of Print Statement After the Recursion:**
    
    - The `System.out.print(n + " ");` statement is executed **only after** the recursive call has returned.
    - Since the recursion reaches the base case first, the smallest value of `n` (which is `1` in this context) is printed last, and the original value of `n` (which is `5` in this example) is printed last after all recursive calls have returned.
---
### Q2. Print Sum of first n natural numbers.

```java
public class SumN{  
    public static void printSum(int i, int n, int sum) {  
        if(i == n) {  
            sum += i;  
            System.out.println(sum);  
            return;  
        }  
        sum += i;  
        printSum(i + 1, n, sum);  
    }  
    public static void main(String[] args) {  
        printSum(1, 5, 0);  
    }  
}
```

---
### Q3. Print factorial of a number n

```java
public class factorial {  
    public static void fact(int n, int product) {  
        if(n == 0) {  
            System.out.println(product);  
            return;  
        }  
  
        product *= n;  
        fact(n - 1, product);  
    }  
    public static void main(String[] args) {  
        fact(5, 1);  
    }  
}
```

---
### Q4. Print Fibonacci sequence till nth term

```java
publlic static void printfibo(int a, int b, int n) {

	if (n == 0) {
		return;
	}
    int c = a + b;
    System.out.print(" " + c);
    printfibo(b, c, n - 1);
}

public static void main(String[] args) {
	int a = 0; int b = 1;
	int n = 7;
	System.out.print(a + " " + b);
	printfibo(a, b, n - 2);
}
```