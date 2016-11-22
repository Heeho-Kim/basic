
#include <stdio.h>
#include <stdlib.h>
int size;
void selectionsort(int a[],int size)
{
 int i,j,t,min,temp;
 printf("\n정렬할 원소 :");
 for(t=0;t<size;t++) printf("%d",a[t]);
 printf("\n\n<<<<<<<<< 선택 정렬 수행>>>>>>>>>\n");
 for(i=0;i<size-1;i++)
 {
  min=i;
  for(j=i+1;j<size;j++)
  {
   if(a[j]<a[min]) min=j;
  }
  temp=a[i];
  a[i]=a[min];
  a[min]=temp;
  printf("\n%d 단계 :",i+1);
  for(t=0;t<size;t++)
   printf("%3d",a[t]);
 }
}
void bubblesort(int a[],int size)
{
 int i,j,t,temp;
 printf("\n정렬할 원소 :");
 for(t=0;t<size;t++)printf("%d",a[t]);
 printf("\n<<<<<<<<<<<< 버블 정렬 수행 >>>>>>>>>>>>");
 for(i=size-1;i>0;i--){
  printf("\n %d 단계 >>",size-i);
  for(j=0;j<=i;j++){
   if(a[j-1]>a[j]){
    temp=a[j-1]; a[j-1]=a[j]; a[j]=temp;
   }
   printf("\n\t");
   for(t=0;t<size;t++) printf("%3d",a[t]);
  }
 }
}
void main()
{
 int sizeofarray,i,input,select;
 int *arr;
 
 printf("만들고 싶은 배열의 원소의 수:");
 scanf("%d",&sizeofarray);
 size=sizeofarray;
 fflush(stdin);
 arr=(int *)malloc(sizeof(int) *sizeofarray);
 for(i=0;i<size;i++)
 {
 scanf("%d",&arr[i]);
 //arr[i]=input;
 }
 printf("선택정렬 1번 버블정렬 2번\n");
 scanf("%d",&select);
 if(select==1)
 {
 selectionsort(arr,size);
 }
 else
 {
  bubblesort(arr,size);
 }
}
