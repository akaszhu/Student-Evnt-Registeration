# Student-Evnt-Registeration
#include <stdio.h>
#include<stdlib.h>

int main ()
{ 
//----------------------------------------------------------------
printf("\n\t\t\t\t\tEVENT MANAGEMENT\n\n");

printf("_________________________________________Event creation_____________________________________");

  printf ("\nEnter number of events :");
  int N;
  scanf ("%d", &N);

  char S[N][30];
  double T[N];
  printf("\n");
  
  printf("\nEnter number of events occur in parallel:");
  int P;scanf("%d",&P);
  
  int Stustr;
  printf("\nEnter total number of students in college:");
  scanf("%d",&Stustr);

printf("\n________________________________________Event Declaration_____________________________________\n");

  printf("\nNote:Enter time in 24 hour format->\n");
  for (int i = 1; i <= N; i++)
    {
      printf ("Enter event name %d-",i);
      scanf ("%s", &S[i][0]);
      printf ("Enter event time %d-",i);
      scanf("%lf",&T[i]);
    }
    printf("\nEvent Name       Time\n");

  for (int i = 1; i <= N; i++)
    {
      printf ("%s  ->%.2f\n",S[i],T[i]);
    } 


//---------------------------------------------------------------------

printf("\n________________________________________Student enrollment_____________________________________\n");
 
 // int N=7;

 int size;
 if(N%2==0){
     size=N/2;
 }else{
     size=(N+1/2);
 }

  int rep1[size],rep2[size];
  int a=0;

 // rep1[0]=0;
 // rep2[0]=0;

 for(int i=0;i<=N;i++){
     for(int j=0;j<=N;j++){
         if(T[i]==T[j]){
             if(i!=j){
                 rep1[a]=i;
                 rep2[a]=j;
                 //printf("%di-%dj",rep1[a],rep2[a]);   
                 a++;
             }
         }
     }
 }



//---------------------------------------------------------------------


//int N=3;

int slot[Stustr][N];
for (int i=0;i<Stustr;i++){
              printf("\n--------------------------------------------------------------------------------------------");
   printf("\n\nEnetr student id :");
   scanf("%d",&slot[i][0]);
   
   if(slot[i][0]<100){
       printf("\nInvalid Roll no kindly enter the roll in the format-eg.110");
        printf("\nEnter correct no:");
       scanf("%d",&slot[i][0]);
   }
   for(int z=i;z<0;z--){
       if(slot[i][0]==slot[z][0]){
           scanf("%d",&slot[i][0]);
           printf("11");
       }else{printf("12");}
   }
   printf("\nEnter event number one by one:\n");
   printf("Note:Enter 0 for next step or Choose limited elements and press )->\n");

   int j=1;

   while(1){
       int temp;
       scanf("%d",&temp);
       if(temp>N){
          printf("\nInvalid event no");
        printf("\nEnter correct no:");
       scanf("%d",&temp);  
       }
         if(temp>0){
           slot[i][j]=temp;
           j++;
              if(j==N+1)
                 {break;}
          }
         else{
           break;
          }
   }//printf("%di %dj",i,j);
   
   printf("\n parallel event: ");int pal;
   for(int r=0;r<P;r++){
      int flag=0;
      for(int a1=1;a1<=N;a1++){
          if(slot[i][a1]==rep1[r]||slot[i][a1]==rep2[r]){
              flag=flag+1;
          }
      }
      if(flag==2){
          printf("%d-%d  ",rep1[r],rep2[r]);
          pal=2;
      }
    }
    if(pal!=2){
        printf("None");
    }
    
    printf("\nselected events ");
      for(int ab=1;ab<j;ab++){
          printf("%d ",slot[i][ab]);
      }
printf("\n\nTo confrim the selected event enter 1 \nTo change selection enter 2 \nTo stop enrolling 3\n\nEnter your choice:");
    int c;
    scanf("%d",&c);
    if(c==1){
        printf("\nFinally selected events ");
      for(int ab=1;ab<j;ab++){
          printf("%d ",slot[i][ab]);
      }
        continue;
    }
    else if(c==2){
          printf("\nEnter student id :");
   scanf("%d",&slot[i][0]);
   printf("Enter event number one by one:\n");
   printf("Note:Enter 0 for next step or Choose limited elements and press )->\n");
   if(slot[i][0]<100){
       printf("\nInvalid Roll no kindly enter the roll in the format-eg.110");
        printf("\nEnter correct no:");
       scanf("%d",&slot[i][0]);
   }

   int j=1;

   while(1){
       int temp;
       scanf("%d",&temp);
       if(temp>N){
          printf("\nInvalid event no");
        printf("\nEnter correct no:");
       scanf("%d",&temp);  
       }
         if(temp>0){
           slot[i][j]=temp;
           j++;
              if(j==N+1)
                 {break;}
          }
         else{
           break;
          }
       }
       printf("\nFinally selected events ");
      for(int ab=1;ab<j;ab++){
          printf("%d ",slot[i][ab]);
      }

    }
    else{
        break;
    } 
    printf("\n");
//---------------------------------------------------------------------
 }printf("\n");
               printf("\n--------------------------------------------------------------------------------------------\n");

 printf("\n________________________________________Student Event list_____________________________________\n");

 for(int d=0;d<Stustr;d++){
     printf("%d ",slot[d][0]);
     for(int d1=1;d1<=N;d1++){
         if(slot[d][d1]<100 & slot[d][d1]>0){
         printf("%d ",slot[d][d1]);
           
         }
     }printf("\n"); 
 }
//---------------------------------------------------------------------
}
