# Leetcode-Product-Of-Array-Except-Self-CS
A solution for "Product of Array except self" on Leetcode in CS

## Explanation
In this problem you have to return an array which contains the product of all of terms in an array except the current position.

This has memory complexity of O(1) because we only store the result array which doesn't count rather than using a prefix and postfix array. This uses a loop first to fill the result array with the prefix, then it mulitiples the result by the postfix.

**Stats**

Runtime: 275 ms, faster than 21.17% of C# online submissions for Product of Array Except Self.

Memory Usage: 48.9 MB, less than 68.68% of C# online submissions for Product of Array Except Self.

## Solution
```cs
public class Solution {
    public int[] ProductExceptSelf(int[] nums) {
        var result = new int[nums.Length];
        
        var prefix = 1;
        for (var i = 0; i < nums.Length; i++) {
            result[i] = prefix;
            prefix *= nums[i];
        }
        
        var postfix = 1;
        for (var i = nums.Length - 1; i >= 0; i--) {
            result[i] *= postfix;
            postfix *= nums[i];
        }
        
        return result;
    }
}
```
