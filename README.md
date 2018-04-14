# Reduce-waiting-time-of-process
The process have to wait for some other process. The waiting time of process is reduced.
This program shows th ediffrence betwwen fcfs waiting time and without fcfs wating time
#include<stdio.h>
#include<conio.h>
int main()
{
	int n,n1,i=0,i1=0,j=0,k=0,t1=0,tt=0,w=0;
	printf("-----------------welcome---------------------------\n");
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
	// this if is implemented to get the starting time of the servicing
	if(t[0]<s[0])
	{
		t1=t[0];
	}
	else if(s[0]<t[0])
	{
		t1=s[0];
	}
	else
	{
		t1=t[0];
	}
	while(i<n||i1<n1)
	{
		if(t[i]<s[i1])
		{
			printf("\nThe teacher wich comes at %d will get the food",t[i]);
			i++;
			j=i;
			t1=t1+2;
			if(i1==n1)
			{
				for(k;k<n;k++)
				{
					w=t1-s[i1];
					tt+=w;
					t1=t1+2;
					printf("\nThe Student wich comes at %d will get the food\t with waiting time %d",s[k],w);
				}
				break;
			}
		}
		else if(s[i1]<t[i])
		{
			w=t1-s[i1];
			tt=tt+w;
			t1=t1+2;
			printf("\nThe Student which comes at %d will get the food\twith waiting time %d",s[i1],w);
			i1++;
			k=i1; 
			if(i1==n1)
			{
				for(j;j<n;j++)
				{

					printf("\nThe teacher which comes at %d will get the food",t[j]);
					t1=t1+2;
				}
				break;
			}
			
		}
		else
		{
			//this will execute when both teacher and stusent arrived at same time
			printf("The teacher comes at %d will got the food",t[i]);
			i++;
			j=i;//used to show the pointer of teacher 
			t1=t1+2;//adding the total time have been taken till now
		}
		
	}
	printf("\nThe average waiting time of the processes %d",(tt/n1));
	//this module is implemented to show the diffrence between fcfs and without fcfs scheduling
	printf("\nWithout FCFS the following schedule will be followed");
	printf("\nThe teachers will get the food first as below:");
	tt=t[0];
	for(i=0;i<n;i++)
	{
		printf("\n%d",t[i]);
		tt=tt+2;
	}
	int a=0;
	printf("\nThe students will get the food after the teachers as follow:");
	for(i=0;i<n1;i++)
	{
		w=tt-s[i];
		tt=tt+2;
		a=a+w;
		printf("\n%dwaiting time%d",s[i],w);
	}
	w=(a/n1);
	printf("\nthe average waiting time of the student is %d",w);
}
