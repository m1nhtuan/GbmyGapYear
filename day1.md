# Leetcode

## Sliding Windows

<pre> ```class Solution {
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
``` </pre>
