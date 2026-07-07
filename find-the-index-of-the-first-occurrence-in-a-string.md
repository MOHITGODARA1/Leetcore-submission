# Find the Index of the First Occurrence in a String

- Topic: String
- Pattern: substring-search
- Submitted from: Leetcore
- Submitted at: 2026-07-07T18:03:31.407Z

## Solution

#include <iostream>
#include <string>
using namespace std;

int main() {
    string hay, needle;
    cin >> hay >> needle;

    if (needle.empty()) {
        cout << 0;
        return 0;
    }

    for (int i = 0; i < hay.size(); i++) {
        if (hay[i] == needle[0]) {
            int left = i;
            int j = 0;

            while (left < hay.size() &&
                   j < needle.size() &&
                   hay[left] == needle[j]) {
                left++;
                j++;
            }

            if (j == needle.size()) {
                cout << i;
                return 0;   // Stop after finding the first occurrence
            }
        }
    }

    cout << -1;
    return 0;
}
