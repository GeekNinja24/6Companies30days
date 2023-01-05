
# Minimum Size Subarray Sum

Given an array of positive integers nums and a positive integer target, return the minimal length of a contiguous subarray [numsl, numsl+1, ..., numsr-1, numsr] of which the sum is greater than or equal to target. If there is no such subarray, return 0 instead.


## Example 1
	Input: target = 7, nums = [2,3,1,2,4,3]
	Output: 2
## Example 2
	Input: target = 4, nums = [1,4,4]
	Output: 1

## Solution
   	class Solution {
	public:
    int minSubArrayLen(int target, vector<int>& nums) {
        long long sum = 0;
        int left = 0, right = 0;
        int min_size = INT_MAX;
        
        for(int n: nums) {
            
            sum += n;

            while (sum >= target) {
                min_size = min(min_size, right - left + 1);
                sum -= nums[left++];
            }

            ++right;
        }

        return min_size == INT_MAX ? 0 : min_size;
    	}
	};


 

 




## Accepted
![Minimum Size Subarray sum](https://user-images.githubusercontent.com/72194471/210839950-3bff8fee-a6d6-427d-98bf-556eaa31b513.PNG)
