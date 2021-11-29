# Some-Typical-Question
## 1.Elimination Game Question
### Input: n = 9
### Output: 6
### Explanation:
### arr = [1, 2, 3, 4, 5, 6, 7, 8, 9]
### arr = [2, 4, 6, 8]
### arr = [2, 6]
### arr = [6]
### class Solution {
### public:
###    int lastRemaining(int n) {
###        int N = n;
###        int diff = 1;
###        bool direction = 0;
###        while(N > 1) {
###            if(N % 2 || direction) {
###                n -= diff;
###            }
###            diff *= 2;
###            N /= 2;
###            direction ^= 1;
###        }
###        return n;
###    }
### };
