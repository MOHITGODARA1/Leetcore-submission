# Valid Palindrome

- Topic: String
- Pattern: two-pointer
- Submitted from: Leetcore
- Submitted at: 2026-07-08T17:57:33.423Z

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
    int left=0;
    int right=s.size()-1;
    bool found=true;
    while(left<=right){
        if(!isalnum(s[left])){
            left++;
            continue;
        }if(!isalnum(s[right])){
            right--;
            continue;
        }
        if(tolower(s[left])!=tolower(s[right])){
            found=false;
            break;
        }            
        left++;
        right--;    
    }
    if(!found){
        cout<<"false";
    }else{
        cout<<"true";
    }

    return 0;
}
