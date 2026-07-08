# Find the Index of the First Occurrence in a String

- Topic: String
- Pattern: substring-search
- Submitted from: Leetcore
- Submitted at: 2026-07-08T09:20:26.424Z

## Solution

#include <iostream>
#include <string>

using namespace std;

int main() {
    string haystack, needle;

    cin >> haystack;
    cin >> needle;

    int n = haystack.length();
    int m = needle.length();

    for (int i = 0; i <= n - m; i++) {
        int j = 0;

        while (j < m && haystack[i + j] == needle[j]) {
            j++;
        }

        if (j == m) {
            cout << i;
            return 0;
        }
    }

    cout << -1;

    return 0;
}
