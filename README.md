# phonekeypad

class Solution {
private:
void num(string digits, string out, int index,vector<string> ans,string mapping[]){
    if(index>=digits.length()){
        ans.push_back(out);
        return ;
    }
    int number=digits[index]-'0';
    string value = mapping[number];
    for(int i=0;i<value.length();i++){
       out.push_back(value[i]);
       num(digits,out,index,ans,mapping);
       out.pop_back();
    }
}

public:
    vector<string> letterCombinations(string digits) {
        vector<string> ans;
        if(digits.length()==0){
            return ans;
        }
        string out="";
        int index=0;
        string mapping[10]={"", "abc", "def", "ghi", "jkl", "mno", "pqrs", "tuv", "wxyz"};
        
        num(digits,out,index,ans,mapping);
        return ans;
    }
};
