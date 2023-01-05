
# Find Missing And Repeating

Given an unsorted array Arr of size N of positive integers. One number 'A' from set {1, 2, …N} is missing and one number 'B' occurs twice in array. Find these two numbers.
## Sample Input
	2
	2 2

## Sample Output
	2 1

    

## Solution
    class Solution{
	public:
    int *findTwoElement(int *arr, int n) {
        vector<bool> nums(n+1, 0);

        int repeated;
        
        int ans[2];

        for(int i = 0; i < n; ++i) {
            int num = arr[i];
            if(nums[num]) {
                ans[0] = num;
            }
            nums[num] = nums[num] ^ 1;
        }

        for(int i = 1; i <= n; ++i) {
            if(nums[i] == 0 && i != ans[0]) {
                ans[1] = i;
                break;
            }
        }

        int *ptr;
        ptr = ans;

        return ptr;

  	  }
	};


 

 




## Accepted
![Find Missing And Repeating](https://user-images.githubusercontent.com/72194471/210838378-c3306c29-0541-4f17-8087-0b3dc2196bdc.PNG)

