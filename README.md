#include<stdio.h>
#include<conio.h>
int main()
{
	int n,n1,i=0,i1=0,j=0,k=0;
	printf("-----------------welcome---------------------------");
	printf("Enter the total number of teachers coming for food");
	scanf("%d",&n);
	printf("Enter the total number of Students coming for food");
	scanf("%d",&n1);
	printf("\nEnter the arrival time of the teachers");
	int t[n],s[n1];
	for(i=0;i<n;i++)
	{
		scanf("%d",&t[i]);
	}
	printf("\nEnter the arrival time of the student");
	for(i=0;i<n1;i++)
	{
		scanf("%d",&s[i]);
	}
	i=0;
	i1=0;
	while(i<n||i1<n1)
	{
		if(t[i]<s[i1])
		{
			printf("\nThe teacher wich comes at %d will get the food",t[i]);
			i++;
			j=i;
			if(i1==n1)
			{
				for(k;k<n;k++)
				{
					printf("\nThe Student wich comes at %d will get the food",s[k]);
				}
				break;
			}
		}
		else if(s[i1]<t[i])
		{
			printf("\nThe Student which comes at %d will get the food",s[i1]);
			i1++;
			k=i1;
			if(i1==n1)
			{
				for(j;j<n;j++)
				{
					printf("\nThe teacher wich comes at %d will get the food",t[j]);
				}
				break;
			}
			
		}
		else
		{
			printf("The teacher comes at %d will got the food",t[i]);
			i++;
			j=i;
		}
		
	}
	//printf("the waiting time of the processes %d");
}
