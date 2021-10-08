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


//算法：试除法找素数.
#include <stdio.h>
#include <math.h>

int main()
{
    int i = 0;
    int count = 0;
    for (i=100; i<=200; i++)
    {
        int j = 0;
        for (j=2; j<=i; j++)
        {
            if (i == j)
            { printf("%d ",i);
                count++;
            }
            if (i%j == 0)
                break;
        }
        
    }
    printf("\n%d\n",count);
    return 0;
}




猜数字游戏
#include <stdio.h>
#include <time.h>
#include <stdlib.h>
void menu()
{
    printf("******************\n");
    printf("***  play=1  *****\n");
    printf("***  exit=0  *****\n");
    printf("******************\n");

}
void game()
{
    int ret = 0;
    int guess = 0;
    ret = rand()%100+1;
    while(1)
    {
        printf("请猜一个数字\n");
        scanf("%d",&guess);
        if (guess>ret)
        {
            printf("猜大了\n");
        }
        else if (guess<ret)
        {
            printf("猜小了\n");
        }
        else
        {
            printf("恭喜你猜对了\n");
            break;
        }
    }
}
int main()
{
    int input = 0;
    srand((unsigned int)time(NULL));
    do
    {
        menu();
        printf("请选择>:");
        scanf("%d",&input);
        switch(input)
        {
            case 1:
                game();
                break;
            case 0:
                printf("退出游戏\n");
                break;
            default:
                printf("选择错误\n");
                break;
        }
    }while (input);
return 0;
}
