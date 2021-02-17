# Sliding Window
```
We will use a method called Sliding Window to count the number of pairs with distance <= guess.

For every possible right, we maintain the loop invariant: left is the smallest value such that nums[right] - nums[left] <= guess. Then, the number of pairs with right as it's right-most endpoint is right - left, and we add all of these up.
```
```C++
class Solution {
public:
    int Count(int target,vector<int>& nums){        //count the number of the pair distance smaller than target
        int Sum=0;
        for (int i=0,j=0;i<nums.size();){
            (j<nums.size())&&(nums[j]-nums[i] <= target) ? j++ : (i++,Sum+=j-i);
        }
        return Sum;  
    }
    int smallestDistancePair(vector<int>& nums, int k) {
        int n,l,r,m;
        n=nums.size();
        sort(nums.begin(),nums.end());
        l=0; r=nums[n-1]-nums[0]; //[l,r] represent the possible pair distance
        while (l<r){            //binary search in possible solution
            m=(l+r)>>1;
            if (Count(m,nums)<k) l=m+1;
            else r=m;
        }
        return r;
    }
};
```
