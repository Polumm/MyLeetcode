```c++
class Solution {
public:
    vector<int> exchange(vector<int>& nums) {
        vector<int> a, b;
        for(int i = 0; i < nums.size(); i++){
            if(nums[i]%2){
                a.push_back(nums[i]);
            }
            else b.push_back(nums[i]);
        }
        vector<int> c(a);
        for(int j = 0; j < b.size(); j++){
            c.push_back(b[j]);
        }
        return c;
    }
};
```

笨比方法，双指针等一下