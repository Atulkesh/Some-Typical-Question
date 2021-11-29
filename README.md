# Some-Typical-Question
## 1.Elimination Game Question
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
