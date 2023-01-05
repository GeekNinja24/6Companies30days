
# Find the position of M-th item
M items are to be delivered in a circle of size N. Find the position where the M-th item will be delivered if we start from a given position K. Note that items are distributed at adjacent positions starting from K.
## Sample Input
    5 8 2

## Sample Output
	4	
    

## Solution
    class Solution {
 	 public:
    int findPosition(int N , int M , int K) {
        if(N == 1) return 1;

        int pos = 1 + (M + K - 2) % N;
        return pos;
    	}
	};


 

 




## Accepted
