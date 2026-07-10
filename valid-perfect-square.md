# Valid Perfect Square

- Topic: Binary Search
- Pattern: classic-binary-search
- Submitted from: Leetcore
- Submitted at: 2026-07-10T14:55:25.707Z

## Solution

#include <iostream>
#include <vector>
#include <string>
#include <algorithm>

using namespace std;

// Write your C++ code here. Read inputs via cin and print output via cout.
int main() {
    // Solution code...
    int n;
    cin>>n;
    int left=1;
    int right=n;
    bool f=false;
    while(left<=right){
        long long mid=left+(right-left)/2;
        if(mid*mid==n){
            f=true;
            break ;
        }
        else if(mid*mid>n){
            right=mid-1;
        }else{
            left=mid+1;
        }
    }
    if(f){
        cout<<"true";
    }else{
        cout<<"false";
    }
    return 0;
}
