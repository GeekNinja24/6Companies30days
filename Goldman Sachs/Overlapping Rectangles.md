
# Q2. Overlapping Rectangles
Given two rectangles, find if the given two rectangles overlap or not. A rectangle is denoted by providing the x and y coordinates of two points: the left top corner and the right bottom corner of the rectangle. Two rectangles sharing a side are considered overlapping. (L1 and R1 are the extreme points of the first rectangle and L2 and R2 are the extreme points of the second rectangle).

Note: It may be assumed that the rectangles are parallel to the coordinate axis.

## Sample Input
    0 10 10 0 5 5 15 0


## Sample Output
    1    

## Solution
    class Solution {
    public:
    int doOverlap(int L1[], int R1[], int L2[], int R2[]) {
       
       if(
           L2[0]-R1[0]>0 || R1[1]-L2[1]>0 || L1[0]-R2[0]>0 || R2[1]-L1[1]>0){
               return 0;
           }
        else{
            return 1;
               
           }
        
     }
    };



 

 




## Accepted
![overlapping Rectangles](https://user-images.githubusercontent.com/72194471/210823334-16fab9f5-0bd8-4ba9-99c2-c2c658d07281.PNG)
