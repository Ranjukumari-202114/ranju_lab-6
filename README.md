# ranju_lab-6


#include <iostream>
using namespace std;

class String{
    
    private:
    
         string word;
    
    public:
    
    String(string x= "")
    {
        word = x;
    }
    string get_string()
    {
        return word;
    }
    void display()
    {
        cout<<"The string is :"<<word<<endl;
    }
    String operator+(String s)
    {
        String result;
        result = word+" "+ s.word;
        return result;
    }
    
    bool compare(string s)
    {
        if(word.length() == s.length())
        {
            for(int i = 0; i<word.length();i++)
            {
                if(word[i] != s[i])
                return false;
            }
            return true;
        }
        return false;
    }
    
};

int main()
{
    string first_string,second_string;
    cout<<"enter first string = ";
    cin>>first_string;
    String s1(first_string);
    s1.display();
    
    cout<<"enter second string = ";
    cin>>second_string;
    String s2(second_string);
    s2.display();
    
    cout<<endl<<"Comaring Both String: ";
    s1.compare(s2.get_string()) ? cout<<"same"<<endl: cout<<"not same"<<endl;
    cout<<endl<<"adding both strings:"<<endl;
    String s3 = s1+s2;
    s3.display();
    cout<<endl;
    return 0;
    
    
}
