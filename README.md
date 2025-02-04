# Leetcode---1800
Maximum Ascending Subarray Sum 
//code in java
public class Solution {
    public int maxAscendingSum(int[] nums) {
        int maxSum = 0;
        int currentSum = 0;
        int previousNum = 0;

        for (int num : nums) {
            if (num > previousNum) {
                currentSum += num;
            } else {
                currentSum = num;
            }
            maxSum = Math.max(maxSum, currentSum);
            previousNum = num;
        }

        return maxSum;
    }

    public static void main(String[] args) {
        Solution solution = new Solution();
        int[] nums1 = {10, 20, 30, 5, 10, 50};
        int[] nums2 = {10, 20, 30, 40, 50};
        int[] nums3 = {12, 17, 15, 13, 10, 11, 12};

        System.out.println(solution.maxAscendingSum(nums1)); // Output: 65
        System.out.println(solution.maxAscendingSum(nums2)); // Output: 150
        System.out.println(solution.maxAscendingSum(nums3)); // Output: 33
    }
}
