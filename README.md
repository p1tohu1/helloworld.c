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
