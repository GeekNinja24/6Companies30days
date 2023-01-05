
# Greatest Common Divisor of Strings
For two strings s and t, we say "t divides s" if and only if s = t + ... + t (i.e., t is concatenated with itself one or more times).

Given two strings str1 and str2, return the largest string x such that x divides both str1 and str2.
## Sample Input/Output
    Input: str1 = "ABCABC", str2 = "ABC"
	Output: "ABC"

	Input: str1 = "LEET", str2 = "CODE"
	Output: ""

    

## Solution
    class Solution {
	public:
    string gcdOfStrings(string str1, string str2) {
        string ans = "";
        string gcd = "";
        
        int i = 0;
        while(i < str1.size() && i < str2.size() && str1[i] == str2[i]) {
            gcd += str1[i];
            ++i;
            if(str1.size() % gcd.size() == 0 && str2.size() % gcd.size() == 0) {
                ans = gcd;
            }
        }
        
        int j = i;
        while(ans.size() && j < str1.size()) {
            if(str1[j] != ans[j % ans.size()]) {
                return "";
            }
            ++j;
        }

        int k = i;
        while(ans.size() && k < str2.size()) {
            if(str2[k] != ans[k % ans.size()]) {
                return "";
            }
            ++k;
        }

        return ans;
   	 }
	};


 

 




## Accepted
