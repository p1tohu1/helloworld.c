# helloworld.c
For recording every code I've typed.
#include <stdio.h>
int main()
{

    {char arr2 [] = {'a','b','c','\0'};
        printf("%s\n",arr2);

}
    return 0;

}
#include <stdio.h>

int main()
{
    int n;
    scanf("%d",&n);
    while (n)
    {
        printf("%d",n % 10);
        n = n / 10;
    }

    return 0;

}
#include <stdio.h>

int main()
{
    char ch = 0;
    while ((ch = getchar()) != EOF)
    {
        putchar(ch + 32);
        printf("\n");
        getchar();
    }
    return 0;
}
int main()
{
    int i;
    printf("冷宗航的周一");
    printf("输入1去厕所，输入2去食堂，输入3去监狱");
    scanf("%d",&i);
    switch (i)
    {
        case 1:
            printf("吃臭狗屎吃撑了");
            break;
        case 2:
            printf("去食堂忘带手机没钱吃饭饿死了");
            break;
        case 3:
            printf("与鄂妃六四击剑取得胜利奖励多坐一年牢");
            break;
    }
    return 0;
}
#include <stdio.h>
int main()
{
    int arr[10]={1,2,3,4,5,6,7,8,9,10};
    int sz = sizeof(arr)/sizeof(arr[0]);
    int left = 0;
    int right = sz - 1;
    while (left<=right)
    {
        int mid = (left + right)/2;
        if (arr[mid]<7)
        {
        left = mid + 1;
        
        }
        else if (arr[mid]>7)
        {
            right = mid - 1;
            
        }
        else{
            printf("找到了，下标为%d\n",mid);
            break;
            
        }
    }
    if (left>right)
    {
        printf("找不到");
    }
    return 0;
}
#include <stdio.h>
#include <string.h>

int main()
{
    int i = 0;
    char password[10] = {0};
    for (i = 0; i < 3; i++)
    {
        printf("请输入密码\n");
        scanf("%s",password);
        if (strcmp(password,"wopazz666") == 0)
        {
            printf("Log in successfully\n");
            break;
        }
    }
    if (i == 3)
    {
        printf("多次错误程序自动销毁");
    }
    return 0;
}
#include <stdio.h>
#include <math.h>

int main()
{
    int i = 0;
    int count = 0;
    for (i = 100; i<=200; i++)
    {
        int j = 0;
        for (j = 2; j < sqrt(i); j++)
        {
            if (i%j == 0)
            {
                break;
            }
           
        }
        if (j > sqrt(i))
        {
            printf("%d ",i);
            count++;
        }
        
    }
    printf("\n%d\n",count);
    return 0;
    
}
