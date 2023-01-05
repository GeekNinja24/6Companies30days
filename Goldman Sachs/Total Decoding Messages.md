
# Total Decoding Messages

A top secret message containing letters from A-Z is being encoded to numbers using the following mapping:

'A' -> 1
'B' -> 2
 .
 .
'Z' -> 26
You are an FBI agent. You have to determine the total number of ways that message can be decoded, as the answer can be large return the answer modulo 109 + 7.

Note: An empty digit sequence is considered to have one decoding. It may be assumed that the input contains valid digits from 0 to 9 and If there are leading 0’s, extra trailing 0’s and two or more consecutive 0’s then it is an invalid string.
## Sample Input
    123

## Sample Output
	3

    

## Solution
    class Solution {
	public:
	    map<int, int> cache;
	    int mod = 1e9+7;
		int CountWays(string str, int n = 0){

		    if(str[0] == '0') return 0;

		    int end = str.size() - n - 1;

		    if(end < 1) return 1;

		    if(cache.count(end)) return cache[end];

		    int count = 0;
		    if(str[end] != '0') {
		        count = CountWays(str, n + 1);
		    }

		    if(str[end-1] == '1' || (str[end-1] == '2' && str[end] <= '6')) {
		        count += CountWays(str, n + 2);
		    }

		    cache[end] = count % mod;

		    return count % mod;
		}

	};


 

 




## Accepted
![Total Decoding Messages](https://user-images.githubusercontent.com/72194471/210834523-5ba26e0c-13e0-49c9-809d-d862a57f3380.PNG)
