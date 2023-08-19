# leet-day36

# Strong Password Checker

## Problem Description

You are given a string representing a password. The goal is to make the password strong according to the given conditions. A password is considered strong if it meets the following criteria:

1. It has at least 6 characters and at most 20 characters.
2. It contains at least one lowercase letter, one uppercase letter, and one digit.
3. It does not contain three repeating characters in a row.

The task is to return the minimum number of steps required to make the password strong. If the password is already strong, return 0.

## Approach

The solution approaches the problem in a systematic manner to optimize the number of modifications required for the password. Here's the step-by-step explanation:

1. **Missing Character Types**: Initially, calculate the number of missing character types (lowercase, uppercase, and digit) in the password. This can be done using the `any_of` function along with lambda functions for each character type.

2. **Repeating Substrings**: Iterate through the password to find repeating substrings of length 3 or more. For each repeating substring, calculate the number of changes required to break the repetition while keeping the length of each segment as close to 3 as possible.

3. **Password Length**: Based on the length of the password, perform the following checks:
   - If the password length is less than 6, add the missing character types and the difference between 6 and the password length to the changes required.
   - If the password length is between 6 and 20, take the maximum of missing character types and changes required from repeating substrings.

4. **Password Length Exceeds 20**: If the password length exceeds 20 characters, calculate the number of deletions required to bring it down to 20. Then, reduce the number of changes based on the deletions while considering repeating substrings.

5. **Return Result**: Return the final count of changes required, which indicates the minimum steps to make the password strong.

## Complexity Analysis

- **Time Complexity**: The solution iterates through the password string once to calculate missing character types and repeating substrings. The overall time complexity is O(n), where n is the length of the password.
- **Space Complexity**: The solution uses a constant amount of extra space to store variables and temporary calculations, resulting in O(1) space complexity.

## Usage

To use the solution, you can create a C++ class or function that implements the provided code. Make sure to include necessary standard libraries like `<algorithm>` and `<cctype>`.

```cpp
#include <algorithm>
#include <cctype>

class Solution {
public:
    int strongPasswordChecker(string password) {
        // Implementation as described in the solution
    }
};
```

You can call the `strongPasswordChecker` function with a password string as an argument to get the minimum steps required to make the password strong.

## Summary

The provided solution optimally addresses the problem of making a password strong by using a systematic approach to handle missing character types and repeating substrings. It aims to minimize the number of modifications required while satisfying the given password criteria. The solution offers a clear and efficient strategy to tackle the problem within the specified constraints.
