# Armstrong Number Checker

## Problem Statement

An **Armstrong number** of three digits is an integer such that the sum of the cubes of its digits is equal to the number itself. For example:

- `153` is an Armstrong number because `1³ + 5³ + 3³ = 153`.
- `123` is **not** an Armstrong number because `1³ + 2³ + 3³ = 36`.

Your task is to determine whether a given number `n` is an Armstrong number.

---

## Solution

We iterate through each digit of the number, calculate its cube, and sum these cubes. Finally, we compare the sum with the original number.

**Steps:**
1. Store the original number in a variable `original`.
2. Initialize `sum = 0`.
3. While `n` is not 0:
    - Extract the last digit: `rem = n % 10`.
    - Add cube of the digit to sum: `sum += rem * rem * rem`.
    - Remove the last digit: `n /= 10`.
4. Compare `sum` with `original`. If equal, return `true`; otherwise, return `false`.

---

## Code (Java)

```java
// User function Template for Java
class Solution {
    static boolean armstrongNumber(int n) {
        int original = n; // store original number
        int sum = 0;
        while(n != 0){
           int rem = n % 10;
           sum += rem * rem * rem;
           n /= 10;
        }
        if(sum == original) return true;
        else return false;
    }
}
Example
Input	Output	Explanation
153	true	1³ + 5³ + 3³ = 153
371	true	3³ + 7³ + 1³ = 371
123	false	1³ + 2³ + 3³ = 36
Constraints

0 <= n <= 999 (for 3-digit numbers)
