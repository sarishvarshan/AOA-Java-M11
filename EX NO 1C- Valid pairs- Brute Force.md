
# EX 1C Valid Pairs using Brute Force Approach
## DATE: 27.04.26
## AIM:
To write a Java program to for given constraints.
Given an integer array nums and an integer k, return the number of pairs (i, j) where i < j such that |nums[i] - nums[j]| == k.

The value of |x| is defined as:

x if x >= 0.
-x if x < 0.

## Algorithm
1. Start the program and import the Scanner class to take user input.
2. Read the number of elements n and then input the array elements.
3. Read the integer value k representing the required absolute difference.
4. Use nested loops to compare each pair (i, j) where i < j and check if |nums[i] - nums[j]| == k.
5. Count and display the total number of valid pairs that satisfy the condition.

## Program:
```
/*
Program to implement Reverse a String
Developed by: SARISH VARSHAN V
Register Number:  212223230196
*/
import java.util.Scanner;
public class CountPairsWithDifference {
    public static int countKDifference(int[] nums, int k) {
        int count=0;
        for(int i=0;i<nums.length;i++){
            for(int j=0;j<nums.length;j++){
                if(nums[i]-nums[j]==k){
                    count++;
                }
            }
        }
        return count;
    }
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int[] nums = new int[n];
        for (int i = 0; i < n; i++) {
            nums[i] = sc.nextInt();
        }
        int k = sc.nextInt();
        int result = countKDifference(nums, k);
        System.out.println(result);
        sc.close();
    }
}

```

## Output:
<img width="619" height="306" alt="image" src="https://github.com/user-attachments/assets/7ec9ad5b-fda9-4b6f-a058-8e5e3484b040" />



## Result:
The program successfully implemented and the expected output is verified.
