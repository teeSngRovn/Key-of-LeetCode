---
Solution-of-TwoSum
---
- In order to match the target,first 

``` C++
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
        vector<int> keys;
        map<int,int> dics;
        for (int i=0;i<nums.size();i++){
            if (dics.count(target-nums[i])!=0) {
                keys.push_back(dics[target-nums[i]]);
                keys.push_back(i);
                return keys;
            }
            dics.insert({nums[i],i});
        }
        
        return keys;
    }
};
```