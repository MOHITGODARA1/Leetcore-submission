# Valid Anagram

- Topic: String
- Pattern: frequency-count
- Submitted from: Leetcore
- Submitted at: 2026-07-09T14:50:32.651Z

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
    string t;
    cin>>s;
    cin>>t;
    vector<int> check(26,0);
    if(s.size()!=t.size()){
        cout<<"false";
        return 0;
    }
    for(int i=0;i<s.size();i++){
        check[s[i]-'a']++;
        check[t[i]-'a']--;
    }
    for(int i=0;i<26;i++){
        if(check[i]!=0){
            cout<<"false";
            return 0;
        }
    }
    cout<<"true";
    return 0;
}
