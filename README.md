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
