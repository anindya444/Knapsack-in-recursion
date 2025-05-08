#include <iostream>
#include <vector>
using namespace std;
int knapsackfun(int w,vector<int>&val,vector<int>&wt,int n)
{
    if (n==0||w==0)
    return 0;
    int pick=0;
    if(wt[n-1]<=w)
    pick=val[n-1]+knapsackfun(w-wt[n-1],val,wt,n-1);
    int notpick=knapsackfun(w,val,wt,n-1);
    return max(pick,notpick);
}

int main()
{
  vector<int> val = {20,40,30};
  vector<int> wt={2,4,3};
  int n=val.size();
  int w=8;
  cout<< knapsackfun(w,val,wt,n);
  return 0;
}
