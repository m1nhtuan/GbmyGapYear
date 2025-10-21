# Day 1

## LeetCode

### Sliding Windows

Problem 1456

```cpp
class Solution {
public:
// ✅ Helper function to check if a character is a vowel
bool isVowel(char c) {
return c == 'a' || c == 'e' || c == 'i' || c == 'o' || c == 'u';
}

    // 🧩 Sliding Window Approach
    int maxVowels(string s, int k) {
        int maxVowel = 0;
        int left = 0;
        int totalVowel = 0;

        for (int right = 0; right < s.length(); right++) {
            // Add rightmost character to the window
            if (isVowel(s[right])) totalVowel++;

            // If window size == k, update result and slide window
            if ((right - left + 1) == k) {
                maxVowel = max(totalVowel, maxVowel);

                // Remove leftmost character when sliding the window
                if (isVowel(s[left])) totalVowel--;
                left++;
            }
        }

        return maxVowel;
    }

};
```

### JS Review

#### 1 Js Fundermental

- **Data types**:
  - **Primitive**: num, string, boolean, undefined, null, symbol, BigInt
  - **Non-Primitive**
- **Dynamic typing**: We don't need to declare the exact type of a variable before using it
- typeof **undefined** is **undefined**
- typeof **null** is **object**
- **const**: must be assigned a value when declared (unlike **var** or **let**, which don’t require initialization)
- 2\*\*3 <=> 2^3
- **type conversion or coercion**

```js
//Conversion
let num = "123";
let converted = Number(num);
//Coercion
console.log("5" - 2);
```

- **NaN**(Not a number) but typeof it is a Number
- A value in JavaScript can be converted to a number, string, or boolean, but undefined and null cannot be meaningfully converted.
- **Coersion** Js automatically convert to number if it ussing operator \*, / , - not with +
- **5 Falsy values** 0, '', undefined, null, NaN
- **==** Strict equality operator doesn't perform type coersion
- **Statment** vs **Expression**

```js
console.log(`Hello ${value}`); // this is a statement and value is a expression
```
