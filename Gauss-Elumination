#include<bits/stdc++.h>
using namespace std;

double a[100][101], ans[100];

int main()
{
    cout.precision(4);
    cout.setf(ios::fixed);
    int n;
    cin >> n;
    for(int i = 1; i <= n; i++) for(int j = 1; j <= n + 1; j++) cin >> a[i][j];
    for(int i = 1; i < n; i++)
    {
        for(int k = i + 1; k <= n; k++)
        {
            if(a[i][i] < a[k][i])
            {
                for(int j = 1; j <= n + 1; j++) swap(a[i][j], a[k][j]);
            }
        }
    }
    for(int i = 1; i < n; i++)
    {
        for(int k = i + 1; k <= n; k++)
        {
            double t = a[k][i] / a[i][i];
            for(int j = 1; j <= n + 1; j++) a[k][j] -= (a[i][j] * t);
        }
    }
    for(int i = n; i >= 1; i--)
    {
        ans[i] = a[i][n + 1];
        for(int j = 1; j <= n; j++)
        {
            if(i != j) ans[i] -= a[i][j] * ans[j];
        }
        ans[i] /= a[i][i];
    }
    for(int i = 1; i <= n; i++) cout << ans[i] << endl;
}
