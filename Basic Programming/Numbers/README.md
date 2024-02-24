# Working with Numbers

1. Highest Common Factor(HCF) / Greatest Common Divisor

```
int gcd(int a, int b) {
    return b == 0 ? a : gcd(b, a % b);
}

```

2. Lowest Common Multiple (LCM)

```
int lcm(int a, int b) {
    return (a / gcd(a, b)) * b;
}

```

3. Binary to Decimal to conversion

```
int binaryToDecimal(String binary) {
    return Integer.parseInt(binary, 2);
}

```

4. Octal to Decimal conversion

```
int octalToDecimal(String octal) {
    return Integer.parseInt(octal, 8);
}

```

5. Hexadecimal to Decimal conversion

```
int hexadecimalToDecimal(String hex) {
    return Integer.parseInt(hex, 16);
}

```

6. Decimal to Binary conversion

```
String decimalToBinary(int decimal) {
    return Integer.toBinaryString(decimal);
}

```

7. Decimal to Octal Conversion

```
String decimalToOctal(int decimal) {
    return Integer.toOctalString(decimal);
}

```

8. Decimal to Hexadecimal Conversion

```
String decimalToHexadecimal(int decimal) {
    return Integer.toHexString(decimal);
}

```

9. Binary to Octal conversion

```
String binaryToOctal(String binary) {
    int decimal = binaryToDecimal(binary);
    return decimalToOctal(decimal);
}

```

10. Octal to Binary conversion

```
String octalToBinary(String octal) {
    int decimal = octalToDecimal(octal);
    return decimalToBinary(decimal);
}

```

11. Quadrants in which a given coordinate lies

```
String findQuadrant(int x, int y) {
    if (x > 0 && y > 0) return "Quadrant 1";
    else if (x < 0 && y > 0) return "Quadrant 2";
    else if (x < 0 && y < 0) return "Quadrant 3";
    else if (x > 0 && y < 0) return "Quadrant 4";
    else return "Origin";
}

```

12. Permutations in which n people can occupy r seats in a classroom

```
int permutations(int n, int r) {
    return factorial(n) / factorial(n - r);
}


```

13. Maximum number of handshakes

```
int maxHandshakes(int n) {
    return n * (n - 1) / 2;
}

```

14. Addition of two fractions

```
String addFractions(int num1, int den1, int num2, int den2) {
    int lcm = lcm(den1, den2);
    int sumNum = (num1 * (lcm / den1)) + (num2 * (lcm / den2));
    int gcd = gcd(sumNum, lcm);
    return (sumNum / gcd) + "/" + (lcm / gcd);
}

```

15. Replace all 0’s with 1 in a given integer

```
int replaceZeroWithOne(int number) {
    String result = String.valueOf(number).replace('0', '1');
    return Integer.parseInt(result);
}

```

16. Can a number be expressed as a sum of two prime numbers

```
boolean canBeExpressedAsSumOfTwoPrimes(int n) {
    for (int i = 2; i <= n / 2; i++) {
        if (isPrime(i) && isPrime(n - i)) {
            return true;
        }
    }
    return false;
}

```

17. Count possible decoding of a given digit sequence

```
int countDecodings(String digits) {
    int n = digits.length();
    int[] dp = new int[n + 1];
    dp[0] = 1;
    dp[1] = digits.charAt(0) != '0' ? 1 : 0;

    for (int i = 2; i <= n; i++) {
        int oneDigit = Integer.parseInt(digits.substring(i - 1, i));
        int twoDigits = Integer.parseInt(digits.substring(i - 2, i));

        if (oneDigit >= 1) {
            dp[i] += dp[i - 1];
        }

        if (twoDigits >= 10 && twoDigits <= 26) {
            dp[i] += dp[i - 2];
        }
    }
    return dp[n];
}

```

18. Calculate the area of a circle

```
double calculateCircleArea(double radius) {
    return Math.PI * radius * radius;
}

```

19. Find the prime numbers between 1 to 100

```
void printPrimesInRange(int start, int end) {
    for (int i = start; i <= end; i++) {
        if (isPrime(i)) {
            System.out.print(i + " ");
        }
    }
    System.out.println();
}

```

20. Calculate the number of digits in an integer

```
int countDigits(int num) {
    return String.valueOf(num).length();
}

```

21. Finding Number of times x digit occurs in a given input

```
int countDigitOccurrences(int number, int x) {
    int count = 0;
    while (number > 0) {
        if (number % 10 == x) {
            count++;
        }
        number /= 10;
    }
    return count;
}

```

22. Finding Roots of a quadratic equation

```
double[] findRoots(double a, double b, double c) {
    double determinant = b * b - 4 * a * c;
    if (determinant > 0) {
        double root1 = (-b + Math.sqrt(determinant)) / (2 * a);
        double root2 = (-b - Math.sqrt(determinant)) / (2 * a);
        return new double[]{root1, root2};
    } else if (determinant == 0) {
        double root = -b / (2 * a);
        return new double[]{root};
    } else {
        return new double[]{};
    }
}

```
