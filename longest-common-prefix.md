# Longest Common Prefix

- Topic: String
- Pattern: vertical-scanning
- Submitted from: Leetcore
- Submitted at: 2026-07-07T04:03:03.020Z

## Solution

#include <iostream>
#include <vector>
#include <string>
using namespace std;

string longestCommonPrefix(vector<string>& strs) {
    if (strs.empty())
        return "";

    for (int i = 0; i < strs[0].size(); i++) {
        char ch = strs[0][i];

        for (int j = 1; j < strs.size(); j++) {
            if (i >= strs[j].size() || strs[j][i] != ch) {
                return strs[0].substr(0, i);
            }
        }
    }

    return strs[0];
}

int main() {
    int n;
    cin >> n;

    vector<string> strs(n);

    for (int i = 0; i < n; i++) {
        cin >> strs[i];
    }

    cout << '"'<<longestCommonPrefix(strs)<<'"';

    return 0;
}
