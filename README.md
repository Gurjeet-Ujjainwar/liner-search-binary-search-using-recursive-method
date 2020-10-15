# liner-search-binary-search-using-recursive-method

What is Binary Search ?

A Binary Search is a sorting algorithm, that is used to search an element in a sorted array. A binary search technique works only on a sorted array, so an array must be sorted to apply binary search on the array. It is a searching technique that is better then the liner search technique as the number of iterations decreases in the binary search.

What is a Linear Search?

A linear search, also known as a sequential search, is a method of finding an element within a list. It checks each element of the list sequentially until a match is found or the whole list has been searched.


program :

#include <stdio.h>
#include <conio.h>
#include <stdlib.h>

main()
{
/* Declare variables - array_of_number,search_key,i,j,low,high*/
    int array[1000],search_key,i,j,n,low,high,location,choice;
    void linear_search(int search_key,int array[1000],int n);
    void binary_search(int search_key,int array[1000],int n);
    clrscr();

/* read the elements of array */

    printf("ENTER THE SIZE OF THE ARRAY:");
    scanf("%d",&n);
    printf("ENTER THE ELEMENTS OF THE ARRAY:\n");
    for(i=1;i<=n;i++)
    {
	scanf("%d",&array[i]);
    }

/* Get the Search Key element for Linear Search */
    printf("ENTER THE SEARCH KEY:");
    scanf("%d",&search_key);

/* Choice of Search Algorithm */
    printf("___________________\n");
    printf("1.LINEAR SEARCH\n");
    printf("2.BINARY SEARCH\n");
    printf("___________________\n");
    printf("ENTER YOUR CHOICE:");
    scanf("%d",&choice);
    switch(choice)
    {
    case 1:
	linear_search(search_key,array,n);
	break;

    case 2:
	binary_search(search_key,array,n);
	break;

    default:
	exit(0);
}
    getch();
    return 0;
}

/* LINEAR SEARCH */
    void linear_search(int search_key,int array[100],int n)
    {

/*Declare Variable */
	int i,location;
        for(i=1;i<=n;i++)
	{
	    if(search_key == array[i])
	    {
		location = i;
    printf("______________________________________\n");
    printf("The location of Search Key = %d is %d\n",search_key,location);
    printf("______________________________________\n");
	}
    }
}

/* Binary Search to find Search Key */
void binary_search(int search_key,int array[100],int n)
{
    int mid,i,low,high;
    low = 1;
    high = n;
    mid = (low + high)/2;
    i=1;
    while(search_key != array[mid])
    {
        if(search_key <= array[mid])
	{
	    low = 1;
	    high = mid+1;
	    mid = (low+high)/2;
	}
	else
	{
	    low = mid+1;
	    high = n;
	    mid = (low+high)/2;
	}
}
    printf("__________________________________\n");
    printf("location=%d\t",mid);
    printf("Search_Key=%d Found!\n",search_key);
    printf("__________________________________\n");

}


Output:

ENTER THE SIZE OF THE ARRAY: 21
ENTER THE ELEMENTS OF THE ARRAY:
10
20
2
3
8
369
4
14
15
24
54
87
-1
-6
54
86
114
136
15
36
54
ENTER THE SEARCH KEY:10
____________________
1. LINEAR SEARCH
2. BINARY SEARCH
____________________
ENTER YOUR CHOICE:2
_____________________________________________
Location =1       Search_Key = 10 Found!
