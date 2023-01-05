
# Nth Ugly number
 Ugly numbers are numbers whose only prime factors are 2, 3 or 5. The sequence 1, 2, 3, 4, 5, 6, 8, 9, 10, 12, 15, … shows the first 11 ugly numbers. By convention, 1 is included. Write a program to find Nth Ugly Number.
## Sample Input
    10
## Sample Output
    12  

## Solution
    class Solution{
    public:	
	    // #define ull unsigned long long
	    /* Function to get the nth ugly number*/
	    ull getNthUglyNo(int n) {
	    vector<long long> ugly_nums(n + 1);
	    ugly_nums[1] = 1;
	    int p2 = 1, p3 = 1, p5 = 1;

	    for(int i = 2; i <= n; ++i) {
	        ugly_nums[i] = min({ 2ll * ugly_nums[p2], 3ll * ugly_nums[p3], 5ll * ugly_nums[p5] });
	        if(ugly_nums[i] == 2ll * ugly_nums[p2]) ++p2;
	        if(ugly_nums[i] == 3ll * ugly_nums[p3]) ++p3;
	        if(ugly_nums[i] == 5ll * ugly_nums[p5]) ++p5;
	    }

	    return ugly_nums.back();
	    }
    };



 

 

