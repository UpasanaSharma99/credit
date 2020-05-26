# credit
To find the credit card type
#include<stdio.h>
#include<stdbool.h>

int rev(long num);
void checkcard(long num);

int main()
{
    rev();
    checkcard();
}

int rev(long num)
{
    int count=0;
    printf("Number:");
    scanf("%l/n",&num);
    int r=0;
    while(num!=0)
    {
        r=(r*10)+(num%10);
        num/=10;
        count++;
    }
    return r;
}

void checkcard(long num)
{
    int c=rev(count);
    num=rev(num);
    int sum=0,var=0;
    long temp=0;

    for(int i=0;i<num;i++)
    {
        var=num%10;
        if(i%2==0)
        {
            temp=var*2;
            if(temp>9)
            {
               sum+=temp-9;
            }
            else
            {
                sum+=temp;
            }
        }
        else
        {
            sum+=var;
        }
        sum/=10;
    }
    if(sum%10==0)
    {
        if(count==15 && (sum==34 || sum==37))
        {
            printf("Amex\n");
        }
        else if(count==16 && (sum>50 && sum<56))
                {
                    printf("Master Card\n");
                }
                else if((count==13 || count==16) && (sum/10==4))
                    {
                        printf("Visa\n");
                    }
                    else
                    {
                        printf("Invalid\n");
                    }

    }
}
