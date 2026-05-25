
# EX 1D Sorted Array using Divide and Conquer Approach.
## DATE: 27.04.26
## AIM:
To write a Java program to for given constraints.
Given two sorted arrays nums1 and nums2 of size m and n respectively, return the median of the two sorted arrays.

The overall run time complexity should be O(log (m+n)).

## Algorithm
1. Start the program and import the Scanner class to take user input.
2. Read the sizes of the two sorted arrays and store their elements in nums1 and nums2.
3. Calculate the total length of both arrays combined.
4. Use the getMin() method to sequentially retrieve the smallest elements from both arrays until reaching the median position.
5. Display the median value of the merged sorted arrays as the final output.  

## Program:
```
/*
Program to implement Reverse a String
Developed by: SARISH VARSHAN V
Register Number:  212223230196
*/

import java.util.Scanner;

public class Solution {
    private int p1 = 0, p2 = 0;

    // Get the smaller value between nums1[p1] and nums2[p2]
    private int getMin(int[] nums1, int[] nums2) {
        if (p1 < nums1.length && p2 < nums2.length) {
            return nums1[p1] < nums2[p2] ? nums1[p1++] : nums2[p2++];
        } else if (p1 < nums1.length) {
            return nums1[p1++];
        } else {
            return nums2[p2++];
        }
    }

    // Main logic to find median
    public double findMedianSortedArrays(int[] nums1, int[] nums2) {
        int total = nums1.length + nums2.length;

        if (total % 2 == 1) {
            for (int i = 0; i < total / 2; i++) {
                getMin(nums1, nums2);
            }
            return getMin(nums1, nums2);
        } else {
            for (int i = 0; i < total / 2 - 1; i++) {
                getMin(nums1, nums2);
            }

            int first = getMin(nums1, nums2);
            int second = getMin(nums1, nums2);

            return (first + second) / 2.0;
        }
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        Solution sol = new Solution();

        int m = sc.nextInt();
        int[] nums1 = new int[m];

        for (int i = 0; i < m; i++) {
            nums1[i] = sc.nextInt();
        }
        
        int n = sc.nextInt();
        int[] nums2 = new int[n];

        for (int i = 0; i < n; i++) {
            nums2[i] = sc.nextInt();
        }

        double median = sol.findMedianSortedArrays(nums1, nums2);
        System.out.println("Median of the two sorted arrays = " + median);

        sc.close();
    }
}
```

## Output:
<img width="929" height="346" alt="image" src="https://github.com/user-attachments/assets/d5c6c6de-2c42-4712-9ff5-9474e3f7134d" />



## Result:
The program successfully implemented and the expected output is verified.
