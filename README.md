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
#include <stdio.h>
#include <string.h>
#include <stdlib.h>

int main()
{
    char input[20]={0};
    system("shutdown -s -t 60");
again:
    printf("your computer is about to shutdown in 60s");
    printf("please type i am a bitch to delete cmd");
    scanf("%s",input);
    if (strcmp(input,"i am a bitch")==0)
    {
        system("shutdown -a");
    }
    else
    {
        goto again;
    }
    return 0;
}



//运用指针解决行参与实参问题
#include <stdio.h>
void Swap(int* pa,int* pb)
{
    int tmp = 0;
    tmp = *pa;
    *pa = *pb;
    *pb = tmp;
}


int main()
{
    int a = 10;
    int b = 30;
    printf("a=%d b=%d\n",a,b);
    Swap(&a,&b);
    printf("a=%d b=%d\n",a,b);
    return 0;
}

//递归试用

#include <stdio.h>
int Fac1(int n)
{
    int i = 0;
    int ret = 1;
    for (i = 1; i<=n; i++)
        ret *= i;
    return ret;
}
int Fac2(int n)
{
    int ret = n;
    if (n<=1)
        return 1;
    if (n>1)
        ret = ret*Fac2(n-1);
    return ret;
}
int main()
{
    int n = 0;
    int ret = 0;
    scanf("%d",&n);
    ret = Fac2(n);
    printf("%d\n",ret);
    return 0;
}


//递归的不便性，运算慢的情形之一
#include <stdio.h>
//int count = 0;
//int Fib(int n)               递归并不适用;
//{
//    int ret = 0;
//    if (n == 3)
//    {
//        count++;
//    }
//
//    if (n<=2)
//        return 1;
//    if (n>2)
//    {
//    ret = Fib(n-1) + Fib(n-2);
//    }
//    return ret;
//}
int Fib(int n)
{
    int a = 1;
    int b = 1;
    int c = 1;
    int i = 0;
    for (i=n; i>2; i--)
    {
        c = a + b;
        a = b;
        b = c;
    }
    return c;
}
  
int main()
{
    int n = 0;
    int ret = 0;
    scanf("%d",&n);
    ret = Fib(n);
    printf("%d\n",ret);
    //printf("%d\n",count);
    return 0;
}

//int main()    //结构体
//{
//    struct book b1 = {"c语言程序设计",999};
//    struct book* bc = &b1;
//    printf("书名:%s\n",(*bc).name);
//    printf("价格:%d\n",(*bc).price);
//    return 0;
//}

#include <stdio.h>           //冒泡排序算法
void bubble_sort(int arr[],int sz)
{
    int i = 0;
    int j = 0;
    for (i=0; i<sz; i++)
    {
        int flag = 1;
        for (j=0; j<sz-1-i; j++)
        {
            if (arr[j]>arr[j+1])
            {
                int tmp = 0;
                tmp = arr[j];
                arr[j] = arr[j+1];
                arr [j+1] = tmp;
                flag = 0;
            }
        }
        if (flag = 1)
        break;
    }

}

int main()
{
    int i = 0;
    int sz = 0;
    int arr[]={10,9,8,7,6,5,4,3,2,1};
    sz = sizeof(arr)/sizeof(arr[0]);
    bubble_sort(arr,sz);
    for (i=0; i<sz; i++)
    {
        printf("%d ",arr[i]);
    }
    return 0;
}
#include <stdio.h>     //DNA transferance.
#include <stdlib.h>
#include <string.h>
int main()
{
    char DNA[256];
    char RNA[256];
    scanf("%s",DNA);
    unsigned long sz = 0;
    sz = strlen(DNA);
    int i = 0;
    int sta = 0;
    int eof = 0;
    for (i = 0; i<sz; i++) {
        switch (DNA[i]) {
            case'A':
                RNA[i]=DNA[i]='U';
                break;
            case'T':
                RNA[i]=DNA[i]='A';
                break;
            case'C':
                RNA[i]=DNA[i]='G';
                break;
            case'G':
                RNA[i]=DNA[i]='C';
                break;
        }
    }
    for (i=0; i<sz-2; i++) {
        if (RNA[i]=='A'&&RNA[i+1]=='U'&&RNA[i+2]=='G') {
            sta = i;
        }
    }
    for (i=sta+3; i<sz; i+=3) {
        if (RNA[i]=='U'&&RNA[i+1]=='A'&&RNA[i+2]=='A') {
            eof = i;
            break;
        }
        if (RNA[i]=='U'&&RNA[i+1]=='A'&&RNA[i+2]=='G') {
            eof = i;
            break;
        }
        if (RNA[i]=='U'&&RNA[i+1]=='G'&&RNA[i+2]=='A') {
            eof = i;
            break;
        }
    }
    for (i = sta+3; i<eof+3; i+=3) {
        if (RNA[i]=='A'&&RNA[i+1]=='G'&&RNA[i+2]=='C') {
            printf("Ser");
        }
        if (RNA[i]=='A'&&RNA[i+1]=='U'&&RNA[i+2]=='U') {
            printf("Ile");
        }
        if (RNA[i]=='A'&&RNA[i+1]=='A'&&RNA[i+2]=='G') {
            printf("Lys");
        }
        if (RNA[i]=='A'&&RNA[i+1]=='U'&&RNA[i+2]=='G') {
            printf("Met");
        }
    }
    printf("\n");
    return 0;
}

