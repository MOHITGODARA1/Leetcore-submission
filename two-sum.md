# Two Sum

- Topic: Hashing
- Pattern: hashmap-complement
- Submitted from: Leetcore
- Submitted at: 2026-07-14T13:12:15.988Z

## Solution

#include <iostream>
#include <vector>
#include <unordered_map>

using namespace std;

vector<int> twoSum(vector<int>& nums, int target) {
    unordered_map<int, int> mp;

    for (int i = 0; i < nums.size(); i++) {
        int complement = target - nums[i];

        if (mp.find(complement) != mp.end()) {
            return {mp[complement], i};
        }

        mp[nums[i]] = i;
    }

    return {};
}

int main() {
    int n;
    cin >> n;

    vector<int> nums(n);

    for (int i = 0; i < n; i++) {
        cin >> nums[i];
    }

    int target;
    cin >> target;

    vector<int> ans = twoSum(nums, target);

    if (!ans.empty()) {
        cout  << ans[0] << " " << ans[1] << endl;
    } else {
        cout << "No valid pair found." << endl;
    }

    return 0;
}
