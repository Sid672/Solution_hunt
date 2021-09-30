Problem: [Link](https://www.codingninjas.com/codestudio/guided-paths/data-structures-algorithms/content/118820/offering/1381870)

Author: [@kr123Manish](https://github.com/kr123Manish)

```C++
long long maxSubarraySum(int arr[], int n)
{
    long long sum=0;
    long long cur_sum=0;
    for(int i=0;i<n;i++){
        cur_sum+=arr[i];
        sum=max(sum,cur_sum);
        if(cur_sum<0){
            cur_sum=0;
        }
    }
    return sum;
}

```