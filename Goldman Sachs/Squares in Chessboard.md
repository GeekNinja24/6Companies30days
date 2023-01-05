
# Squares in N*N Chessboard

Find the total number of squares in a N x N chessboard.

## Formula
Let f(n-1) and f(n) be the number of squares from (N-1).(N-1) to N.N chessboard respectively.

∴ f(n)= k+ f(n-1)
where k is increment in number of squares from (N-1).(N-1) to N.N chessboard

 k = n(n+1)/2 +n(n+1)/2 - n = n²

∴ f(n) = n² + f(n-1)

∴ f(n) = n² + (n-1)² + (n-2)² + .... + 2² + 1² + 0² 

∴ f(n) = n(n+1)(2n+1)/6     //formula for sum of n square numbers.

## Sample Input
    2


## Sample Output
    5

## Solution
    class Solution{
        public:
        long long squareInChessBoard(long long N){

            long long ans = N*(N+1)*(2N+1)/6;
            return ans;

        }
    };



 

 


## Accepted

