# Add Strings

- Topic: String
- Pattern: string-as-number-simulation
- Submitted from: Leetcore
- Submitted at: 2026-07-10T15:53:49.941Z

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
    string t;
    cin>>t;
    int curry=0;
    int s1=s.size()-1,s2=t.size()-1;
    string ans="";
    while(s1>=0 && s2>=0){
        int sum=(s[s1]-'0')+(t[s2]-'0')+curry;
        if(sum>9){
            curry=1;
            sum-=10;
        }else{
            curry=0;
        }
        ans+=to_string(sum);
        s1--;
        s2--;
    }
    while(s1>=0){
        int sum=(s[s1]-'0')+curry;
        if(sum>9){
            curry=1;
            sum-=10;
        }else{
            curry=0;
        }
        ans+=to_string(sum);
        s1--;
    }
    while(s2>=0){
        int sum=(t[s2]-'0')+curry;
        if(sum>9){
            curry=1;
            sum-=10;
        }else{
            curry=0;
        }
        ans+=to_string(sum);
        s2--;
    }
    if(curry==1){
        ans+=to_string(curry);
    }
    reverse(ans.begin(),ans.end());
    cout<<'"'<<ans<<'"';
    return 0;
}
