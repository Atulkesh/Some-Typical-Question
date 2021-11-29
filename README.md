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

## 1.Longest file path
### Input: input = "dir\n\tsubdir1\n\tsubdir2\n\t\tfile.ext"
### Output: 20
### Explanation: We have only one file, and the absolute path is "dir/subdir2/file.ext" of length 20.
### int lengthLongestPath(string input) {
###        int ans = 0, n = input.size(), level = 0;
###        unordered_map<int, int> A;
###        A[0] = 0;
###        for(int i=0; i<n; i++)
###        {
###            int start = i;
###            while(i<n && input[i]!='\n' && input[i]!='\t')
###                i++;
###            if(i>=n || input[i]=='\n')
###            {
###                string t = input.substr(start, i-start);
###                if(t.find('.')!=string::npos)
###                {
###                    ans= max(ans, A[level]+(int)t.length());
###                }
###                else
###                {
###                    level++;
###                    A[level] = A[level-1] + t.length()+1;
###                }
###                level = 0;
###            }
###            else
###                level++;
###        }
###        return ans;
###    }
