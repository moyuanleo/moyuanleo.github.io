# 42.接雨水
[试题链接](https://leetcode-cn.com/problems/trapping-rain-water/)

一般方法

```cpp
class Solution {
public:
    int trap(vector<int>& height) {
        int ans = 0;
        int length = height.size();
        if(length == 0) {
            return 0;
        }
        int max_left[length], max_right[length];
        max_left[0] = height[0];
        for(int i = 1; i < length; i++) {
            max_left[i] = max(height[i],max_left[i - 1]);
        }
        max_right[length - 1] = height[length - 1];
        for(int i = length - 2; i >= 0; i--) {
            max_right[i] = max(height[i],max_right[i + 1]);
        }
        for(int i = 0; i < length; i++) {
            int temp = min(max_left[i],max_right[i]) - height[i];
            ans += temp > 0 ? temp : 0;
        }
        return ans;
    }
};
```

耗时短

```cpp
class Solution {
public:
    int trap(vector<int>& height)
    {
        int left = 0, right = height.size() - 1;
        int ans = 0;
        int left_max = 0, right_max = 0;
        while (left < right) {
            if (height[left] < height[right]) {
                height[left] >= left_max ? (left_max = height[left]) : ans += (left_max - height[left]);
                ++left;
            }
            else {
                height[right] >= right_max ? (right_max = height[right]) : ans += (right_max - height[right]);
                --right;
            }
        }
        return ans;
    }
};
```