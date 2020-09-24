# Maximum-Subsequence-codechef
#include <bits/stdc++.h>
using namespace std;

int main()
{

    int t;
    cin>>t;
    while(t--){
        int n;
        cin>>n;
        vector<int> A(n);
        for(int i=0;i<n;i++)
        cin>>A[i];
        int count=0;
        long long sum=0;
        vector<int> positive(n);
        for(int i=n-1;i>=0;i--){
            positive[i]=count;
            if(A[i]>=0){ count++;
            sum+=A[i];
            }
        }
        if(count==0) {
            cout<<0<<"\n"<<0<<endl;
        }
        else{
        count=0;
        vector<int> out;
        for(int i=0;i<n;i++){
                if(A[i]<0){
                    count++;
                    out.push_back(i);
                }
            if(count==positive[i]){
                for(int j=i+1;j<n;j++){
                        if(A[j]>=0)
                    out.push_back(j);
                }
                break;
            }
        }
        cout<<sum<<endl;
        cout<<out.size()<<" ";
        for(int i=0;i<out.size();i++){
            cout<<out[i]+1<<" ";
        }
        cout<<endl;
        }
    }

}







