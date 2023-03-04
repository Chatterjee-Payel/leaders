# leaders
class Solution{
    //Function to find the leaders in the array.
    public:
    vector<int> leaders(int a[], int n){
        // Code here
       int leader=a[n-1];
       int arr[n];
       vector<int>ans;
       int count=0;
       arr[count]=leader;
       for(int i=n-2;i>=0;i--)
       {
           if(a[i]>=leader)
           {
               leader=a[i];
               count++;
               arr[count]=leader;
           }
       }
       int start=0; int end=count;
       while(start<=end)
       {
           swap(arr[start],arr[end]);
           end--;
           start++;
       }
       for(int i=0;i<=count;i++){
           ans.push_back(arr[i]);
           
       }
       return ans;
    }
};
