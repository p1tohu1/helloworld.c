//算法：二分查找
#include <stdio.h>
int main()
{
    int arr[10] = {1,2,5,8,20,29,32,54,65,76};
    int k = 76;
    int left = 0;
    int right = 9;
    int mid = (right + left)/2;
    while (left<=right)
    {
        if (arr[mid]<k)
            left = mid + 1;
        if (arr[mid]>k)
            right = mid - 1;
        if (arr[mid]==k)
        {
            printf("下标为 %d\n",mid);
            break;
        }
        mid = (left+right)/2;    //mid需要重新赋值！！！
    }
    if (left>right)
    {
        printf("该数据不存在于数列中\n");
    }
    return 0;
}
