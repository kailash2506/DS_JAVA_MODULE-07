# Ex9 Finding the Longest Length of Nested Set in a Permutation Array
## DATE: 18-02-2026
## AIM:
To write a program that finds the length of the longest set s[k] defined as s[k] = { nums[k], nums[nums[k]], nums[nums[nums[k]]], … },where the iteration stops before a duplicate element occurs.

The task is to return the maximum size among all such sets.
## Algorithm
1.Create a visited array to mark elements already used in any set.

2.For each index k, if it is not visited, start building the set S[k].

3.Keep moving to nums[current], marking each element as visited.

4.Count each step until you reach a visited element (duplicate).

5.Update the maximum count found so far and return it.  

## Program:
```
/*
program that removes all nodes from a linked list whose value matches a given integer (val) and returns the new head of the modified linked list.
Developed by: Kailash Kumar S
RegisterNumber: 212223220041
*/
import java.util.*;
public class ArrayNestingMain {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String input = sc.nextLine().trim();
        input = input.replace("nums =", "").replace("[", "").replace("]", "").trim();
        String[] parts = input.split(",");
        int[] nums = new int[parts.length];

        for (int i = 0; i < parts.length; i++) {
            nums[i] = Integer.parseInt(parts[i].trim());
        }
        Solution sol = new Solution();
        int result = sol.arrayNesting(nums);
        System.out.println(result);
        sc.close();
    }
}
class Solution {
    public int arrayNesting(int[] nums) {
        int maxlen = 0;
        boolean[] visited = new boolean[nums.length];
        for (int i = 0; i < nums.length; i++) {
            if (!visited[i]) {
                int count = 0;
                int curr = i;
                while (!visited[curr]) {
                    visited[curr] = true;
                    curr = nums[curr];
                    count++;
                }
                maxlen = Math.max(maxlen, count);
            }
        }
        return maxlen;

    }
}
   
*/

```

## Output:

<img width="483" height="90" alt="image" src="https://github.com/user-attachments/assets/542673ef-ce05-4ca5-bf07-bca1eb7733d0" />


## Result:
The program successfully computes the longest length of the nested set s[k] for the given permutation array.
