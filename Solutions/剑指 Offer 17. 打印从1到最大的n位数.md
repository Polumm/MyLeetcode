```c++
class Solution {
public:
    vector<int> printNumbers(int n) {
        int wei = 1;
        for(int i = n; i > 0; i--){
            wei *= 10;
        }
        vector<int> vec;
        for(int j = 1; j < wei; j++){
            vec.push_back(j);
        }
        return vec;
    }
};
```

