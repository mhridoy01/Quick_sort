# Quick_sort

/*In this code we implement the quick sort
 and we save a text file in desktop .
 by using this code we open the file and reed the text file and we sort the data.
 */
 #include<bits/stdc++.h>
 using namespace std;
 int divide(int arr[],int p,int r)
 {
     int i=p-1,pivot=arr[r];
     for(int j=p;j<r;j++)
     {
         if(arr[j]<=pivot)
         {
             i++;
             swap(arr[j],arr[i]);
         }
     }
     i++;
     swap(arr[i],arr[r]);
     return i;
 }
 void quic_sort(int arr[],int p,int r)
 {
     if(p<r)
     {
         int q = divide(arr,p,r);
         quic_sort(arr,p,q-1);
         quic_sort(arr,q+1,r);
     }
 }
 int main()
 {
     freopen("input.txt","r",stdin);
     int n,arr[100];
     cin>>n;
     for(int i=1;i<=n;i++)
        cin>>arr[i];
        quic_sort(arr,1,n);
     for(int i=1;i<=n;i++)
        cout << arr[i] << endl;
     return 0;
 }

