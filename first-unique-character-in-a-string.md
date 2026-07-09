# First Unique Character in a String

- Topic: String
- Pattern: frequency-count
- Submitted from: Leetcore
- Submitted at: 2026-07-09T15:40:27.191Z

## Solution

#include <iostream>
#include <vector>
#include <string>
#include <algorithm>

using namespace std;

// Write your C++ code here. Read inputs via cin and print output via cout.
int main() {
    // Solution code...
    string s;
    cin>>s;
    vector<int> ch(26,0);
    for(int i=0;i<s.size();i++){
        ch[s[i]-'a']++;
    }
    for(int i=0;i<s.size();i++){
        if(ch[s[i]-'a']==1){
            cout<<i;
            return 0;
        }
    }
    cout<<-1;
    return 0;
}
