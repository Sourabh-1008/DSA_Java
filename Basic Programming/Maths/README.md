# Maths Basice Programs

1. Positive or Negative number

```
void checkNumber(int num) {
    if (num > 0) {
        System.out.println(num + " is positive");
    } else if (num < 0) {
        System.out.println(num + " is negative");
    } else {
        System.out.println("The number is zero");
    }
}

```

2. Even or Odd number

```
 void checkEvenOdd(int num) {
    if (num % 2 == 0) {
        System.out.println(num + " is even");
    } else {
        System.out.println(num + " is odd");
    }
}

```

3. Sum of First N Natural numbers

```
int sumOfFirstNNaturalNumbers(int N) {
    return N * (N + 1) / 2;
}

```

5. Sum of numbers in a given range

```
int sumInRange(int start, int end) {
    int sum = 0;
    for (int i = start; i <= end; i++) {
        sum += i;
    }
    return sum;
}

```

6. Greatest of two numbers

```
int greatestOfTwo(int a, int b) {
    return a > b ? a : b;
}

```

7. Greatest of the Three numbers

```
int greatestOfThree(int a, int b, int c) {
    return Math.max(a, Math.max(b, c));
}

```

8. Leap year or not

```
boolean isLeapYear(int year) {
    return (year % 4 == 0 && year % 100 != 0) || (year % 400 == 0);
}

```

9. Prime number

```
boolean isPrime(int num) {
    if (num <= 1) {
        return false;
    }
    for (int i = 2; i <= Math.sqrt(num); i++) {
        if (num % i == 0) {
            return false;
        }
    }
    return true;
}

```

10. Prime number within a given range

```
void printPrimeNumbersInRange(int start, int end) {
    for (int i = start; i <= end; i++) {
        if (isPrime(i)) {
            System.out.print(i + " ");
        }
    }
    System.out.println();
}

```

11. Sum of digits of a number

```
int sumOfDigits(int num) {
    int sum = 0;
    while (num != 0) {
        sum += num % 10;
        num /= 10;
    }
    return sum;
}

```

12. Reverse of a number

```
int reverseNumber(int num) {
    int reversed = 0;
    while (num != 0) {
        reversed = reversed * 10 + num % 10;
        num /= 10;
    }
    return reversed;
}

```

14. Palindrome number

```
boolean isPalindrome(int num) {
    return num == reverseNumber(num);
}

```

15. Armstrong number

```
boolean isArmstrong(int num) {
    int original = num, sum = 0;
    int n = Integer.toString(num).length();
    while (num != 0) {
        int digit = num % 10;
        sum += Math.pow(digit, n);
        num /= 10;
    }
    return sum == original;
}

```

16. Armstrong number in a given range

```
void printArmstrongNumbersInRange(int start, int end) {
    for (int i = start; i <= end; i++) {
        if (isArmstrong(i)) {
            System.out.print(i + " ");
        }
    }
    System.out.println();
}

```

17. Fibonacci Series upto nth term

```
void printFibonacciSeries(int n) {
    int a = 0, b = 1;
    System.out.print(a + " " + b + " ");
    for (int i = 2; i < n; i++) {
        int next = a + b;
        System.out.print(next + " ");
        a = b;
        b = next;
    }
    System.out.println();
}

```

18. Find the Nth Term of the Fibonacci Series

```
int findNthFibonacciTerm(int n) {
    if (n <= 1) {
        return n;
    }
    int a = 0, b = 1;
    for (int i = 2; i < n; i++) {
        int next = a + b;
        a = b;
        b = next;
    }
    return b;
}

```

19. Factorial of a number

```
int factorial(int n) {
    if (n == 0) {
        return 1;
    }
    int result = 1;
    for (int i = 1; i <= n; i++) {
        result *= i;
    }
    return result;
}

```

20. Power of a number

```
double power(double base, int exponent) {
    return Math.pow(base, exponent);
}

```

21. Factor of a number

```
void printFactors(int num) {
    System.out.print("Factors of " + num + ": ");
    for (int i = 1; i <= num; i++) {
        if (num % i == 0) {
            System.out.print(i + " ");
        }
    }
    System.out.println();
}

```

22. Finding Prime Factors of a number

```
void printPrimeFactors(int num) {
    System.out.print("Prime factors of " + num + ": ");
    for (int i = 2; i <= num; i++) {
        while (num % i == 0) {
            System.out.print(i + " ");
            num /= i;
        }
    }
    System.out.println();
}

```

23. Strong number

```
boolean isStrongNumber(int num) {
    int original = num;
    int sum = 0;
    while (num > 0) {
        int digit = num % 10;
        sum += factorial(digit);
        num /= 10;
    }
    return sum == original;
}

```

24. Perfect number

```
boolean isPerfectNumber(int num) {
    int sum = 0;
    for (int i = 1; i < num; i++) {
        if (num % i == 0) {
            sum += i;
        }
    }
    return sum == num;
}

```

25. Perfect Square

```
boolean isPerfectSquare(int num) {
    int sqrt = (int) Math.sqrt(num);
    return sqrt * sqrt == num;
}

```

26. Automorphic number

###### An automorphic number is a number whose square ends in the same digits as the number itself.

```
boolean isAutomorphic(int num) {
    int square = num * num;
    while (num > 0) {
        if (num % 10 != square % 10) {
            return false;
        }
        num /= 10;
        square /= 10;
    }
    return true;
}

```

27. Harshad number

###### A Harshad number is an integer that is divisible by the sum of its digits.

```
boolean isHarshad(int num) {
    int sum = 0, original = num;
    while (num > 0) {
        sum += num % 10;
        num /= 10;
    }
    return original % sum == 0;
}

```

28. Abundant number

###### An abundant number is a number for which the sum of its proper divisors is greater than the number itself.

```
boolean isAbundant(int num) {
    int sum = 1; // Start with 1 because it's always a divisor
    for (int i = 2; i <= Math.sqrt(num); i++) {
        if (num % i == 0) {
            sum += i;
            if (i != num / i) {
                sum += num / i;
            }
        }
    }
    return sum > num;
}

```

29. Friendly pair

###### Two numbers are a friendly pair (or amicable numbers) if the sum of the proper divisors of each is equal to the other number.

```
// Helper function to find the sum of divisors
int sumOfDivisors(int num) {
    int sum = 1;
    for (int i = 2; i <= Math.sqrt(num); i++) {
        if (num % i == 0) {
            sum += i;
            if (i != num / i) {
                sum += num / i;
            }
        }
    }
    return sum;
}

// Function to check if a pair is friendly
boolean isFriendlyPair(int a, int b) {
    return sumOfDivisors(a) == b && sumOfDivisors(b) == a;
}

```
