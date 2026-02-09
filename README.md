# C6
#include<stdio.h>
void main()
{
    int array[10];
    int i,j,num,temp,keynum;
    int low,mid,high;
    printf("enter the value of num\n");
    scanf("%d",&num);
    printf("enter the elements one by one \n");
    for(i=0;i<num;i++)
    {
        scanf("%d",&array[i]);
    }
    printf("input array elements\n");
    for(i=0;i<num;i++)
    {
        printf("%d\n",array[i]);
    }
    for(i=0;i<num;i++)
    {
        for(j=0;j<(num-i-1);j++)
        {
            if(array[j]>array[j+1])
            {
                temp=array[j];
                array[j]=array[j+1];
                array[j+1]=temp;
            }
        }
    }
    printf("sorted array is ....\n");
    for(i=0;i<num;i++)
    {
        printf("%d\n",array[i]);
    }
    printf("enter the element to be searched\n");
    scanf("%d",&keynum);
    low=1;
    high=num;
    do
    {
        mid=(low+high)/2;
        if(keynum<array[mid])
        high=mid-1;
        else if(keynum>array[mid])
        low=mid+1;
    } while(keynum!=array[mid]&&low<=high);
    if(keynum==array[mid])
    {
        printf("SEARCH SUCCESSFULL\n");
    }
    else
    {
        printf("SEARCH FAILED\n");
    }
}
