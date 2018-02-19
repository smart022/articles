本题大意是对给定一串字符串将其中字符依次改变大小写后存入容器后返回。

初想是个排序问题，算C(k,n)，但是想来不知道用什么结构表示，就算设好了

还是很复杂，故这题目看了看讨论区，非常受教，解题思路都是用递归回溯法

非常精巧。

排列结果可用二叉树的子节点表示。故这题就转化为树状递归。

**注意**：在大小写转化时还用到了一个trick，异或^32??

```c++
class Solution {
public:
    vector<string> letterCasePermutation(string S) {
        vector<string> ret;
        backtrack(ret,0,S);
        return ret;
    }
    
    void backtrack(vector<string> &cot, int i, string &str){
        if(i== str.size()){
            cot.push_back(str);
            return;
        }
        backtrack(cot, i+1, str);
        if(isalpha(str[i])){
        	// toggle case
            str[i] ^= (1 << 5);
            backtrack(cot,i+1,str);
            // return previous case
            str[i] ^= (1 << 5);
        }   
    }
};
```

