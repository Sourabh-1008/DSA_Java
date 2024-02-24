# String Basice Programs 

1. Check whether a character is a vowel or consonant?
```
public static boolean isVowel(char c) {
        return "AEIOUaeiou".indexOf(c) != -1;
}
```
2. Check whether a character is a alphabet or not?
```
 public static boolean isAlphabet(char c) {
        return (c >= 'A' && c <= 'Z') || (c >= 'a' && c <= 'z');
}
```
3. Find the ASCII value of a character?
```
public static int asciiValue(char c) {
        return (int) c;
}
```
4. Length of the string without using strlen() function?
```
 public static int lengthOfString(String str) {
        int length = 0;
        for (char c : str.toCharArray()) {
            length++;
        }
        return length;
}
```
5. Toggle each character in a string?
```
public static String toggleString(String str) {
        StringBuilder toggled = new StringBuilder();
        for (char c : str.toCharArray()) {
            if (Character.isUpperCase(c)) {
                toggled.append(Character.toLowerCase(c));
            } else {
                toggled.append(Character.toUpperCase(c));
            }
        }
        return toggled.toString();
 }
```
6. Count the number of vowels 
```
  public static int countVowels(String str) {
        int count = 0;
        for (char c : str.toCharArray()) {
            if (isVowel(c)) {
                count++;
            }
        }
        return count;
}
```
7. Remove the vowels from a String
```
 public static String removeVowels(String str) {
        return str.replaceAll("[AEIOUaeiou]", "");
}
```
8. Check if the given string is Palindrome or not
```
public static boolean isPalindrome(String str) {
        int i = 0, j = str.length() - 1;
        while (i < j) {
            if (str.charAt(i) != str.charAt(j)) {
                return false;
            }
            i++;
            j--;
        }
        return true;
}
```
9. Print the given string in reverse order
```
  public static String reverseString(String str) {
        return new StringBuilder(str).reverse().toString();
}
```
10. Remove all characters from string except alphabets 
```
 public static String keepAlphabetsOnly(String str) {
        return str.replaceAll("[^a-zA-Z]", "");
    }
```
11. Remove spaces from a string 
```
 public static String removeSpaces(String str) {
        return str.replaceAll("\\s+", "");
    }
```
12. Remove brackets from an algebraic expression
```
 public static String removeBrackets(String str) {
        return str.replaceAll("[(){}\\[\\]]", "");
    }
```
13. Count the sum of numbers in a string
```
public static int sumOfNumbers(String str) {
        int sum = 0;
        String[] parts = str.split("\\D+");
        for (String part : parts) {
            if (!part.isEmpty()) {
                sum += Integer.parseInt(part);
            }
        }
        return sum;
}
```
14. Capitalize the first and last character of each word of a string
```
public static String capitalizeFirstAndLast(String str) {
        String[] words = str.split("\\s");
        StringBuilder result = new StringBuilder();
        for (String word : words) {
            if (word.length() > 1) {
                result.append(Character.toUpperCase(word.charAt(0)))
                      .append(word.substring(1, word.length() - 1))
                      .append(Character.toUpperCase(word.charAt(word.length() - 1)))
                      .append(" ");
            } else {
                result.append(word.toUpperCase()).append(" ");
            }
        }
        return result.toString().trim();
    }
```
15. Calculate frequency of characters in a string
```
 public static void frequencyOfCharacters(String str) {
        int[] freq = new int[256]; // Assuming ASCII
        for (char c : str.toCharArray()) {
            freq[c]++;
        }
        for (int i = 0; i < 256; i++) {
            if (freq[i] > 0) {
                System.out.println((char) i + ": " + freq[i]);
            }
        }
    }
```
16. Find non-repeating characters in a string
```
 public static String nonRepeatingCharacters(String str) {
        int[] freq = new int[256]; // Assuming ASCII
        for (char c : str.toCharArray()) {
            freq[c]++;
        }
        StringBuilder nonRepeating = new StringBuilder();
        for (char c : str.toCharArray()) {
            if (freq[c] == 1) {
                nonRepeating.append(c);
            }
        }
        return nonRepeating.toString();
    }
```
17. Check if two strings are Anagram or not 
```
public static boolean areAnagrams(String str1, String str2) {
        int[] count = new int[256]; // Assuming ASCII
        for (char c : str1.toCharArray()) {
            count[c]++;
        }
        for (char c : str2.toCharArray()) {
            count[c]--;
        }
        for (int i : count) {
            if (i != 0) {
                return false;
            }
        }
        return true;
    }
```
18. Replace a sub-string in a string
```
public static String replaceSubstring(String str, String oldSubStr, String newSubStr) {
        return str.replace(oldSubStr, newSubStr);
    }
```
19. Replacing a particular word with another word in a string
```
public static String replaceWord(String str, String oldWord, String newWord) {
        return str.replaceAll("\\b" + oldWord + "\\b", newWord);
    }
```
20. Check if two strings match where one string contains wildcard characters
```
 public static boolean matchWithWildcards(String str, String pattern) {
        // Simple version. A full implementation may need recursion or dynamic programming.
        return str.matches(pattern.replace("?", ".?").replace("*", ".*?"));
    }
```
