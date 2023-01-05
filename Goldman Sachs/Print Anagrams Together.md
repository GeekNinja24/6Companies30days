
# Print Anagrams Together
Given an array of strings, return all groups of strings that are anagrams. The groups must be created in order of their appearance in the original array. Look at the sample case for clarification.


## Sample Input
    5
    act god cat dog tac


## Sample Output
    act cat tac 
    god dog     

## Solution
    class Solution{
    public:
    vector<vector<string> > Anagrams(vector<string>& string_list) {
        map<string,vector<string> >m;
        for(int i =0;i<string_list.size();i++){
            string str = string_list[i];
            sort(str.begin(),str.end());
            m[str].push_back(string_list[i]);
        }
        vector<vector<string>> ans;
        for(auto &item :m){
            ans.push_back(item.second);
            }
        return ans;
    }
    };



 

 




## Accepted
