//mergesort




#include<bits/stdc++.h>
using namespace std;

void Swap(int *a,int *b)
{
    int t=*a;
    *a=*b;
    *b=t;
}

int Partition(int arr[],int start,int end)
{
    int pivot= arr[end];
    int p_index=start;
    for(int i=start;i<end;i++)
    {
        if(arr[i]<=pivot){
            Swap(&(arr[i]) , &(arr[p_index]));
            p_index++;
        }

    }
    Swap(&(arr[p_index]) , &(arr[end]));
    return p_index;
}


void quick_sort(int arr[],int start,int end)
{
    if(start<end)
    {
        int p_index=Partition(arr,start,end);
        quick_sort(arr,start,p_index-1);
        quick_sort(arr,p_index+1,end);
    }
}


int main()
{
    int arr[]={7,2,1,6,8,5,3,4};
    int n=sizeof(arr)/sizeof(arr[0]);
    for(int i=0;i<n;i++)
        cout<<arr[i]<<" ";
    cout<<endl;
    quick_sort(arr,0,n);
    for(int i=0;i<n;i++)
        cout<<arr[i]<<" ";
    return 0;
}
