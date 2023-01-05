
# Run Length Encoding
Given a string, Your task is to complete the function encode that returns the run length encoded string for the given string. eg if the input string is “wwwwaaadexxxxxx”, then the function should return “w4a3d1e1x6″. You are required to complete the function encode that takes only one argument the string which is to be encoded and returns the encoded string.
## Sample Input
    aaaabbbccc

## Sample Output
    a4b3c3  

## Solution
    string encode(string src)
    {     
        char last = '-';
        string ans = "";
        int count = 0;

        for(char c: src) {
            if(c != last) {
              if(count) {
                     ans += to_string(count);
                }
                 ans += c;
                count = 1;
            }
            else {
                 ++count;
             }
            last = c;
        }
        ans += to_string(count);
  
        return ans;
    }



 

 




## Accepted
![Runlength Encoding](https://user-images.githubusercontent.com/72194471/210827973-c5541f0f-4988-4c8c-b6c9-f2adce8342c7.PNG)


