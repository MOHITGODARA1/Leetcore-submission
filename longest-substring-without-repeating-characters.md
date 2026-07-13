# Longest Substring Without Repeating Characters

- Topic: String
- Pattern: sliding-window
- Submitted from: Leetcore
- Submitted at: 2026-07-13T14:28:01.366Z

## Solution

#include <iostream>
#include <vector>
#include <string>
#include <algorithm>
#include <unordered_map>

using namespace std;

// Write your C++ code here. Read inputs via cin and print output via cout.
int main() {
    // Solution code...
    string s;
    cin>>s;
    unordered_map<int,int> count;
    int left=0,ans=0;
    for(int i=0;i<s.size();i++){
        count[s[i]]++;
        while(count[s[i]]>1){
            count[s[left]]--;
            left++;
        }
        ans=max(ans,i-left+1);
    }
    cout<<ans;
    return 0;
}
