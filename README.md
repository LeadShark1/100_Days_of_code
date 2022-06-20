# 100_Days_of_code
20/06/2022
Day1
Today I am starting 100 Days of Code . Now I'll continue it.

66. Plus One
You are given a large integer represented as an integer array digits, where each digits[i] is the ith digit of the integer. The digits are ordered from most significant to least significant in left-to-right order. The large integer does not contain any leading 0's.

Increment the large integer by one and return the resulting array of digits.

 

Example 1:

Input: digits = [1,2,3]
Output: [1,2,4]
Explanation: The array represents the integer 123.
Incrementing by one gives 123 + 1 = 124.
Thus, the result should be [1,2,4].
Example 2:

Input: digits = [4,3,2,1]
Output: [4,3,2,2]
Explanation: The array represents the integer 4321.
Incrementing by one gives 4321 + 1 = 4322.
Thus, the result should be [4,3,2,2].
Example 3:

Input: digits = [9]
Output: [1,0]
Explanation: The array represents the integer 9.
Incrementing by one gives 9 + 1 = 10.
Thus, the result should be [1,0].
 

Constraints:

1 <= digits.length <= 100
0 <= digits[i] <= 9
digits does not contain any leading 0's.



class Solution {
public:
    vector<int> plusOne(vector<int>& digits) {
        
        int n = digits.size();
        
        if (digits[n-1] < 9) {(digits[n-1] = digits[n-1]+1);}
        
        else if (digits[n-1] == 9) {
            
            for (int i=n-1; i>=0; i--){
            
                if(digits[i] == 9){
                    digits[i] = 0;
                }else if (digits[i+1] == 0 && digits[i] <9){ 
                    digits[i] = digits[i]+1;
                    break;
                }     
                if (digits[0] == 0){ 
                    digits.resize(n+1,0);
                    digits[0] =1;
                }
            }
        }
        
         return digits;
        
        /////////////////////  INTEGER OVERFLOW  //////////////////////////
        
//         int num =0;
        
//        for (int i=0; i<digits.size(); i++){
//             num = num*10+digits[i];
//         }
//         num = num+1;
        
//         digits.clear();
        
//         while (num) {
//         digits.push_back(num%10);
//             num /= 10;
//         } reverse(digits.begin(), digits.end());
//         return digits;
    }
};
