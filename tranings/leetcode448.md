此题没有限定的话很简单，但是有限制空间和O(n)的时间所有有点棘手。

看讨论，一致得出的最优方案很巧妙。用给定的数组做标定数组，出现过的位置

取负，没出现的数字位置会保持为正。

```c++
class Solution {
public:
    vector<int> findDisappearedNumbers(vector<int>& nums) {
        vector<int> ret;
        int i;
        for(auto p:nums){
            i = abs(p) -1;
            nums[i] = nums[i]>0? -nums[i]:nums[i];
        }
        
        for(int j=0;j<nums.size();j++){
            if(nums[j]>0)
                ret.push_back(j+1);
        }
        return ret;
    }
};
```

