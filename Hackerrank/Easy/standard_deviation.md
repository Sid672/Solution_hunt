Problem: [Link](https://www.hackerrank.com/challenges/s10-standard-deviation)

Author: [@shivesh01](https://github.com/shivesh01)


```c++
#include <bits/stdc++.h>
using namespace std;

string ltrim(const string &);
string rtrim(const string &);
vector<string> split(const string &);

/*
 * Complete the 'stdDev' function below.
 *
 * The function accepts INTEGER_ARRAY arr as parameter.
 */

/-------------------------------------------------------------------------
void stdDev(vector<int> arr) {
    // Print your answers to 1 decimal place within this function
    float mean = 0;
    //mean
    for(int i  = 0 ; i<arr.size(); i++)
    {
        mean += arr[i];
    }
    mean /= arr.size();
    // cout<<mean<<"\n";


    // sum of variance
    float x = 0;
    for (int i = 0; i<arr.size(); i++ )
    {
        x += (arr[i] - mean)*(arr[i] - mean);
    }
    // cout<<x<<"\n";


    // standard deviation
    float stand_dev = 0;
    stand_dev =(sqrt(x/arr.size()));
    cout<<fixed;
    cout<<setprecision(1);
    cout<<stand_dev<<"\n";


}
/-------------------------------------------------------------------------


int main()
{
    string n_temp;
    getline(cin, n_temp);

    int n = stoi(ltrim(rtrim(n_temp)));

    string vals_temp_temp;
    getline(cin, vals_temp_temp);

    vector<string> vals_temp = split(rtrim(vals_temp_temp));

    vector<int> vals(n);

    for (int i = 0; i < n; i++) {
        int vals_item = stoi(vals_temp[i]);

        vals[i] = vals_item;
    }

    stdDev(vals);

    return 0;
}

string ltrim(const string &str) {
    string s(str);

    s.erase(
        s.begin(),
        find_if(s.begin(), s.end(), not1(ptr_fun<int, int>(isspace)))
    );

    return s;
}

string rtrim(const string &str) {
    string s(str);

    s.erase(
        find_if(s.rbegin(), s.rend(), not1(ptr_fun<int, int>(isspace))).base(),
        s.end()
    );

    return s;
}

vector<string> split(const string &str) {
    vector<string> tokens;

    string::size_type start = 0;
    string::size_type end = 0;

    while ((end = str.find(" ", start)) != string::npos) {
        tokens.push_back(str.substr(start, end - start));

        start = end + 1;
    }

    tokens.push_back(str.substr(start));

    return tokens;
}
```
