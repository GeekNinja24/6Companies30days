
# Q3. Count the subarrays having product less than k
Given an array of positive numbers, the task is to find the number of possible contiguous subarrays having product less than a given number k.
## Sample Input
    4 10
    1 2 3 4

## Sample Output
    7   

## Solution
    class Solution{
        public:
        int countSubArrayProductLessThanK(const vector<int>& a, int n, long long k) {
        long long int start=0,end=0,count=0,prod=1;
           while(end<n){
               prod*=a[end];
               while(start<n and prod>=k){
                   prod=prod/a[start];
                   start++;
               }
               if(prod<k)
               count+=end-start+1;
              
               end++;
           }
           return count;   
        }
    };



 

 




## Accepted
![count the subarrays](https://user-images.githubusercontent.com/72194471/210826853-da9c6f8d-561b-4e0e-8eeb-403019ce17b2.PNG)
