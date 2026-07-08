# Two Sum

- Topic: Array
- Pattern: hash-map
- Submitted from: Leetcore
- Submitted at: 2026-07-08T05:34:11.705Z

## Solution

#include <iostream>
#include <vector>
#include <unordered_map>

using namespace std;

int main() {
    int n;
    cin >> n;

    vector<int> nums(n);
    for (int i = 0; i < n; i++) {
        cin >> nums[i];
    }

    int target;
    cin >> target;

    unordered_map<int, int> mp;

    for (int i = 0; i < n; i++) {
        int complement = target - nums[i];

        if (mp.find(complement) != mp.end()) {
            cout << "[" << mp[complement] << ", " << i << "]";
            return 0;
        }

        mp[nums[i]] = i;
    }

    return 0;
}
