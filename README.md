#include<stdio.h>
int main()
{
int page_faults=0,  page_reference[100], frames, pages, p[100],i,j,k,t,n;
printf("\nenter length of refernce string:");
scanf("%d",&pages);
printf("\nenter page reference sequence:");
for(i=0;i<n;i++)
{
 printf(" value of the no:",i+1);
scanf("%d",&page_reference[i]);
}
printf("\nenter no of frames:");
scanf("%d",&frames);
int temp[frames];
for(i=0;i<pages;i++)
{
temp[i]= -1;
}
for (i=0;i<pages;i++)
{
 t =0;
for(j=0;j<frames;j++)
{ 
   if(page_reference[i]==temp[j])
{
       t ++;
      page_faults--;
}
}
 page_faults++;
if((page_faults<=frames) && (t==0))
{
   temp[i]= page_reference[i];
}
 else if(t==0)
{
temp[(page_faults-1)%frames]=page_reference[i];
}
printf("\n");
for(j=0;j<frames;j++)
{
printf("%d",temp[j]);
}
}
printf("\npage faults:\t%d\n", page_faults);
return 0;
}
