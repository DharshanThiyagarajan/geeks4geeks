# geeks4geeks #cpp #alternative numbs
#include <bits/stdc++.h>
using namespace std;

class Solution {

  public:
    vector<int> alternateSort(vector<int>& arr) {
        vector <int> a;
        sort(arr.begin(),arr.end());
        int i=0;
        int j=arr.size()-1;
        while(i<j)
        {
            a.push_back(arr[j]);
            a.push_back(arr[i]);
            j--;
            i++;
        }
        if (i==j)
        {
            a.push_back(arr[i]);
        }
        return a;
    }
};


int main() {
    string ts;
    getline(cin, ts);
    int t = stoi(ts);
    while (t--) {
        vector<int> arr;
        string input;
        getline(cin, input);
        stringstream ss(input);
        int number;
        while (ss >> number) {
            arr.push_back(number);
        }
        Solution obj;
        vector<int> ans = obj.alternateSort(arr);
        for (int i = 0; i < ans.size(); i++) {
            cout << ans[i] << " ";
        }
        cout << endl;
        cout << "~" << endl;
    }
    return 0;
}
