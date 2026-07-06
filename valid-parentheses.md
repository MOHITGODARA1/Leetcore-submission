# Valid Parentheses

- Topic: String
- Pattern: stack-matching
- Submitted from: Leetcore
- Submitted at: 2026-07-06T17:05:50.045Z

## Solution

#include <iostream>
#include <vector>
#include <string>
#include <algorithm>
#include <stack>
using namespace std;

// Write your C++ code here. Read inputs via cin and print output via cout.
int main() {
    // Solution code...
    string s;
    cin>>s;
    stack<char> st;
    for(int i=0;i<s.size();i++){
      if(s[i]=='(' || s[i]=='{' || s[i]=='['){
        st.push(s[i]);
      }
      if(s[i]==')'){
        if(st.top()=='('){
          st.pop();
        }
      }
      if(s[i]=='}'){
        if(st.top()=='{'){
          st.pop();
        }
      }
      if(s[i]==']'){
        if(st.top()=='['){
          st.pop();
        }
      }
    }
    if(st.empty()){
      cout<<"true";
    }else{
      cout<<"false";
    }
    return 0;
}
