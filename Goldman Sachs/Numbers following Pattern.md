
# Number following a pattern

Given a pattern containing only I's and D's. I for increasing and D for decreasing.

Devise an algorithm to print the minimum number following that pattern.

Digits from 1-9 and digits can't repeat.
## Sample Input
   	D

## Sample Output
	21

    

## Solution
    class Solution{   
	public:
    string printMinNumberForPattern(string S){

        vector<int>num(S.size() + 1, 0);
        num[0] = 1;

        int max_int = 1;

        for(int i = 0; i < S.size(); ++i) {
            if(S[i] == 'I') {
                ++max_int;
                num[i + 1] = max_int;
            }

            int r = 0;
            while(i - r >= 0 && S[i - r] == 'D') {
                num[i - r + 1] = num[i - r];
                ++num[i - r];
                max_int = max(max_int, num[i - r]);
                ++r;
            }
        }

        for(auto n : num) {
            cout << n;
        }

        return "";
   	 }
	};


 

 




## Accepted
![Numbers following Pattern](https://user-images.githubusercontent.com/72194471/210835494-55aff87d-c594-441b-94a2-9981947e1b28.PNG)
