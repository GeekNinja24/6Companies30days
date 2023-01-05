
# Array Pair Sum Divisibility Problem


Given an array of integers and a number k, write a function that returns true if given array can be divided into pairs such that sum of every pair is divisible by k.

## Sample Input
	4 6
	9 7 5 3
## Sample Output
	True

## Solution
   	class Solution {
  	public:
    bool canPair(vector<int> nums, int k) {

        if(nums.size() % 2) return false;

        unordered_map<int, int> rem;

        for(int n: nums) {
            int r = n%k;

            if(r && rem.count(k - r) && rem[k - r] > 0) {
                --rem[k - r];
                rem[0] += 2;
            }
            else {
                ++rem[r];
            }
        }
    
        return rem[0] == nums.size();
    }
	};


 

 




## Accepted
