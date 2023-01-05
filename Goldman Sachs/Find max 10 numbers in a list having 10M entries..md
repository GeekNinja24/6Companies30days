
# Max 10 numbers in a list having 10M entries (K largest elements)

Given an array of N positive integers, print k largest elements from the array.
## Sample Input
	5 2
	12 5 787 1 23

## Sample Output
	787 23

    

## Solution
    class Solution
	{
    public:
    vector<int> kLargest(int arr[], int n, int k)
    {
        priority_queue<int, vector<int>, greater<int> >pq;

        for(int i = 0; i < k; ++i) {
            pq.push(arr[i]);
        }

        for(int i = k; i < n; ++i) {
            if(pq.top() < arr[i]) {
                pq.pop();
                pq.push(arr[i]);
            }
        }

        vector<int> ans;
        while (!pq.empty()) {
            ans.push_back(pq.top());
            pq.pop();
        }

        reverse(ans.begin(), ans.end());

        return ans;
    	}
	};


 

 




## Accepted
