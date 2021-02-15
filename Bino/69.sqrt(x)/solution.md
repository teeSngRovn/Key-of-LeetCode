# Binary Search
```
Using binary search to approach the limit of the solution.
```
``` C++
class Solution {
public:
    int mySqrt(int x) {     //Acc:Accuracy
        double lo,hi,m,Acc;
        Acc=0.0000001;
        hi=x;lo=0;
        if (x==1) return 1;
        while (hi-lo>Acc){
            m=(hi+lo)/2;
            if (x-m*m==0) return m;
            x-m*m>0 ? lo=m : hi=m;
        }
        return int(hi);
    }
};
```
