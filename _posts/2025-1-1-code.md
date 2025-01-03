---
layout: post
title: code
date: 2025
description: a long code
c: true
---

See this code
```c
#include <stdio.h>
#include <math.h>

int fard(int x);
int primnum(int x);
int beutnum(int x);
int mirror(int x);
int taghs(int x);

int main()
{

    int a = 0, b = 0, c = 0,sum = 0, aa, i;

    scanf("%d", &a);

    for (i = 3; i <= a; i++)
    {
        b = fard(i);

        if (b == 1)
        {

            c = beutnum(i);

            if (c == 1)
            {

                sum += i;
            }
        }

        if (b == 0)
        {
            continue;
        }
    }

    aa = mirror(sum);

    if (aa == 0)
    {
        printf("NOT FOUND!");
    }
    else if (aa != 0)
    {
        printf("%d", aa);
    }
}

int fard(int x) // this function is checking odd number
{

    if (x % 2 == 0)
    {
        return 0;
    }

    else if (1 > 0)
    {
        return 1;
    }
}

int primnum(int x) // this function is checking of prime number
{

    int i, b = 0;

    for (i = 2; i <= x; i++)
    {
        if (x % i == 0)
        {
            b++;
        }
    }
    if (b < 2)
    {
        return 1;
    }
    else return 0 ;
}

int beutnum(int x) // this function is returning beutifull number
{
    int a,i,c;
    a = taghs(x);
    

        for (i = 3; i <= x; i++)
    {
        if (x % i == 0)
        {

            c = primnum(i);
            if (c == 1)
            {
                if (a == i){break;}
                else continue;
               
            }
        }
    }

    if (a == i){return 1;}

    else return 0 ;


    
}

int taghs(int x) // this function giving number of prime taghs
{
    int a, i, q = 0;

    for (i = 3; i <= x; i++)
    {
        if (x % i == 0)
        {

            a = primnum(i);
            if (a == 1)
            {
                q++;
            }
        }
    }

    return q;
}

int mirror(int x) // this function revers the sum of number in end
{

    int a = 0, i, x1, b, c, s = 0;

    x1 = x;

    while (x1 > 0)
    {

        x1 /= 10;
        a++;
    }

    for (i = 1; i <= a; i++)
    {

        b = x % 10;
        x /= 10;
        c = b * pow(10, a - i);
        s += c;
    }

    return s;
}
```
