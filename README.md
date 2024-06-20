Largest Sum Contiguous Subarray in Java
Here, in this page we will discuss the program to find the largest sum contiguous subarray in Java. We will discuss two different ways in this page for finding such subarray.
Largest Sum Contiguous Sub-Array in Java
The problem of finding the largest sum contiguous subarray in a given array involves identifying a subarray within the array that has the highest sum of its elements. This means we are searching for a continuous subarray in the given array that has the maximum possible sum. For example, consider the following array:
arr = [-2, -3, 4, -1, -2, 1, 5, -3]
The largest sum contiguous subarray in this array is [4, -1, -2, 1, 5], which has a sum of 7. The problem of finding the largest sum contiguous subarray has a well-known algorithm called Kadane’s algorithm. The algorithm has a time complexity of O(n) and can be easily implemented in Java.
Largest Sum Contiguous Sub-Array in Java
Method Discussed :
Method 1 : Brute Force Approach.
Method 2 : Using Kadane’s Algorithm
Method 1 :
Declare a variable say res = INT_MIN.
Run a loop from index 0 to n.
Declare a variable sum = 0;
Run a nested loop from index i to n.
Set sum += arr[j].
And res = max(res, sum)
After Complete Iteration print res.
Time and Space Complexity :
Time Complexity : O(n2)
Space Complexity : O(1)
DSA desktop gif
Related Pages
Given an array which consists of only 0, 1 and 2

Move all the negative elements to one side of the array

Find the Union and Intersection of the two sorted arrays

Find Largest sum contiguous Subarray

Minimize the maximum difference between heights 

Method 1 : Code in Java
Run
import java.util.*;

public class Main {
    public static void main(String[] args) {
        int[] arr = {-2, -3, 4, -1, -2, 1, 5, -3};
        int n = arr.length;
        int res = Integer.MIN_VALUE;
        for (int i = 0; i < n; i++) {
            int sum = 0;
            for (int j = i; j < n; j++) {
                sum += arr[j];
                res = Math.max(sum, res);
            }
        }
        System.out.println(res);
    }
}

Output
7
Method 2 :
Create variable say max_sum that hold the required maximum sum of subarray and curr_sum and initialize max_sum with INT_MIN and curr_sum with 0.
Now, iterate over the array, and for every ith value of the array, add it to curr_sum, and comapre it with max_sum like,
if(max_sum < curr_sum) max_sum = curr_sum.
Now, check if curr_sum <0 then set curr_sum to 0.
After complete iteration we will get the result that store in max_sum variable.
Time and Space Complexity :
Time Complexity : O(n)
Space Complexity : O(1)
Method 2 : Code in Java
Run
import java.util.*;

public class Main {
    public static void main(String[] args) {
        int[] arr = {-2, -3, 4, -1, -2, 1, 5, -3};
        int n = arr.length;
        int max_sum = Integer.MIN_VALUE, curr_sum = 0;

        for (int i = 0; i < n; i++) {
            curr_sum += arr[i];
            if (max_sum < curr_sum)
                max_sum = curr_sum;

            if (curr_sum < 0)
                curr_sum = 0;
        }

        System.out.println(max_sum);
    }
}

Output
7
