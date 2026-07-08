# Length of Last Word

- Topic: String
- Pattern: reverse-traversal
- Submitted from: Leetcore
- Submitted at: 2026-07-08T17:28:36.672Z

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
    getline(cin,s);
    int ans=0;
    for(int i=s.size()-1;i>=0;i--){
        if(s[i]!=' '){
            ans++;
        }
        if(ans>0 && s[i]==' '){
            break;
        }
    }
    cout<<ans;
    return 0;
}
