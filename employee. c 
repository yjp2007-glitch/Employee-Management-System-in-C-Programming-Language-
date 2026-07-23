
#include<stdio.h>
#include<stdlib.h>
#include<string.h>

struct employee
{
   int id;
   char name[50];
   char dept[20];
   float salary;
};
void input(int n)
{
    FILE *fp;
    struct employee e;
     int i;
    fp=fopen("employee.dat","wb");
    for(i=0;i<n;i++)
    {
        printf("Enter employee id=");
        scanf("%d",&e.id);
        printf("Enter employee name=");
        scanf("%s",e.name);
        printf("Enter employee department name=");
        scanf("%s",e.dept);
        printf("Enter employee salary=");
        scanf("%f",&e.salary);

        fwrite(&e,sizeof(e),1,fp);
    }
    fclose(fp);
}

void sortbyid()
{
    FILE *fp,*fp2;
    struct employee e[100],temp;
    int i=0,j,n;
    fp=fopen("employee.dat","rb");
     if(fp==NULL)
     {
        printf("File cannot be opened");
        return ;
     }

    while(fread(&e[i],sizeof(e[i]),1,fp)==1)
    {
        i++;
    }
    fclose(fp);
    n=i;
    for(i=0;i<n-1;i++)
    {
        for(j=i+1;j<n;j++)
        {
            if(e[i].id > e[j].id)
            {
               temp=e[i];
               e[i]=e[j];
               e[j]=temp;
            }
        }
    }
        fp=fopen("employee.dat","wb");
        for(i=0;i<n;i++)
        {
            fwrite(&e[i],sizeof(e[i]),1,fp);
        }
        fp2=fopen("sort.dat","wb");
    for(i=0;i<n;i++)
    {
    fwrite(&e[i],sizeof(e[i]),1,fp2);
    }
    fclose(fp2);
        fclose(fp);
        printf("\n File is sorted by id\n");
}
/* void input(int *p, int n)
{
    int i;
    printf("Enter elements=");
    for(i=0;i<n;i++)
    {
        scanf("%d",(p+i));
    }
}

void sortbyid(int *p, int n)
{
     int i,j,temp;
     for(i=0;i<n-1;i++)
     {
        for(j=i+1;j<n;j++)
        {
            if(*(p+i)>*(p+j))
            {
                temp=*(p+i);
                *(p+i)=*(p+j);
                *(p+j)=temp;
            }
        }
 }
}

void display(int *p, int n)
{
    int i;
    for(i=0;i<n;i++)
    {
        printf("%d",*(p+i));
    }
}*/

void sortbyname()
{
    FILE *fp;
    struct employee e[100],temp;
    int i=0,j,n;
    fp=fopen("employee.dat","rb");
    fp=fopen("employee.dat","rb");

     if(fp==NULL)
     {
        printf("File cannot be opened");
        return ;
     }
    while(fread(&e[i],sizeof(e[i]),1,fp)==1)
    {
        i++;
    }
    fclose(fp);
    n=i;
    for(i=0;i<n-1;i++)
    {
        for(j=i+1;j<n;j++)
        {
            if(strcmp(e[i].name, e[j].name)>0)
            {
               temp=e[i];
               e[i]=e[j];
               e[j]=temp;
            }
      }
    }
        fp=fopen("employee.dat","wb");
        for(i=0;i<n;i++)
        {
            fwrite(&e[i],sizeof(e[i]),1,fp);
        }
        fclose(fp);
        printf("\n File is sorted by name\n");
}
void sortbydeptname()
{
    FILE *fp;
    struct employee e[100],temp;
    int i=0,j,n;

    fp=fopen("employee.dat","rb");
     fp=fopen("employee.dat","rb");
     if(fp==NULL)
     {
        printf("File cannot be opened");
        return ;
     }
    while(fread(&e[i],sizeof(e[i]),1,fp)==1)
    {
        i++;
    }
    fclose(fp);
    n=i;
    for(i=0;i<n-1;i++)
    {
        for(j=i+1;j<n;j++)
        {
            if(strcmp(e[i].dept, e[j].dept)>0)
            {

               temp=e[i];
               e[i]=e[j];
               e[j]=temp;
          }
        }
    }
        fp=fopen("employee.dat","wb");
        for(i=0;i<n;i++)
        {
            fwrite(&e[i],sizeof(e[i]),1,fp);
        }
        fclose(fp);
        printf("\n File is sorted by Dept_name\n");

}

void sortbysalary()
{
    FILE *fp;
    struct employee e[100],temp;
    int i=0,j,n;
    fp=fopen("employee.dat","rb");
    fp=fopen("employee.dat","rb");
     if(fp==NULL)
     {
        printf("File cannot be opened");
        return ;
     }

    while(fread(&e[i],sizeof(e[i]),1,fp)==1)
    {
        i++;
    }
    fclose(fp);
    n=i;
    for(i=0;i<n-1;i++)
    {
        for(j=i+1;j<n;j++)
        {
            if(e[i].salary > e[j].salary)
            {
               temp=e[i];
               e[i]=e[j];
               e[j]=temp;
            }
        }
    }
        fp=fopen("employee.dat","wb");
        for(i=0;i<n;i++)
        {
            fwrite(&e[i],sizeof(e[i]),1,fp);
        }
        fclose(fp);
        printf("\n File is sorted by salary\n");
}

void display()
{
     FILE *fp;
    struct employee e;

    fp=fopen("employee.dat","rb");
    
     if(fp==NULL)
     {
        printf("File cannot be opened");
        return ;
     }
        printf("Id\tName\tDept\tsalary\n");
        while(fread(&e,sizeof(e),1,fp)==1)
        {
        printf("%d\t%s\t%s\t%.2f\n",e.id,e.name,e.dept,e.salary);
        }
    fclose(fp);
}

void deletebyid()
{
    FILE*fp,*fd;
    struct employee e;
    int id,found=0;

     fp=fopen("employee.dat","rb");
    fd=fopen("delete.dat","wb");

    printf("Enter id number to delete=");
    scanf("%d",&id);
    while(fread(&e,sizeof(e),1,fp)==1)
    {
        if(e.id==id)
            found=1;
        else
            fwrite(&e,sizeof(e),1,fd);
    }

    fclose(fp);
fclose(fd);

      fp=fopen("employee.dat","wb");
      fd=fopen("delete.dat","rb");
      while(fread(&e,sizeof(e),1,fd)==1)

      {
        fwrite(&e,sizeof(e),1,fp);
      }
      fclose(fp);
        fclose(fd);
        if(found)
        printf("Record deleted\n");
        else
        printf("Record does not found\n");

}

void deletebyname()
{
 FILE*fp,*fd;
    struct employee e;
    int found=0;
    char name[50];

     fp=fopen("employee.dat","rb");
    fd=fopen("delete.dat","wb");

    printf("Enter name to delete=");
    scanf("%s",name);
    while(fread(&e,sizeof(e),1,fp)==1)
    {
        if(strcmp(e.name,name)==0)
            found=1;
        else
            fwrite(&e,sizeof(e),1,fd);
    }
    fclose(fp);
    fclose(fd);

      fp=fopen("employee.dat","wb");
      fd=fopen("delete.dat","rb");

      while(fread(&e,sizeof(e),1,fd)==1)
      {
        fwrite(&e,sizeof(e),1,fp);
      }

      fclose(fp);
        fclose(fd);
        if(found)
        printf("Record deleted\n");
        else
        printf("Record does not found\n");
}

void deletebydeptname()
{
    FILE*fp,*fd;
    struct employee e;
    int found=0;
    char name[50];

     fp=fopen("employee.dat","rb");
    fd=fopen("delete.dat","wb");

    printf("Enter dept_name to delete=");
    scanf("%s",name);
    while(fread(&e,sizeof(e),1,fp)==1)
    {
        if(strcmp(e.dept,name)==0)
            found=1;
        else
            fwrite(&e,sizeof(e),1,fd);
    }

    fclose(fp);
    fclose(fd);

      fp=fopen("employee.dat","wb");
      fd=fopen("delete.dat","rb");
      while(fread(&e,sizeof(e),1,fd)==1)
      {
        fwrite(&e,sizeof(e),1,fp);
      }

      fclose(fp);
        fclose(fd);
        if(found)
        printf("Record deleted\n");
        else
        printf("Record does not found\n");
}

void deletebysalary()
{
    FILE*fp,*fd;
    struct employee e;
    int found=0;
    float salary;

     fp=fopen("employee.dat","rb");
    fd=fopen("delete.dat","wb");

    printf("Enter salary to delete=");
    scanf("%f",&salary);
    while(fread(&e,sizeof(e),1,fp)==1)
    {
        if(e.salary==salary)
            found=1;
        else
            fwrite(&e,sizeof(e),1,fd);
    }

    fclose(fp);
    fclose(fd);

      fp=fopen("employee.dat","wb");
      fd=fopen("delete.dat","rb");
      while(fread(&e,sizeof(e),1,fd)==1)
      {
        fwrite(&e,sizeof(e),1,fp);
      }
      fclose(fp);
        fclose(fd);
        if(found)
        printf("Record deleted\n");
        else
        printf("Record does not found\n");

}

void searchbyname()

{
    FILE *fp;
    struct employee e;
    int flag=0;
    char name[50];
         fp=fopen("employee.dat","rb");
         printf("Enter employee name to search=");
         scanf("%s",name);

         printf("Id\tName\tDept\tsalary\n");
    while(fread(&e,sizeof(e),1,fp)==1)
    {
        if(strcmp(e.name , name)==0)
        {
        printf("%d\t%s\t%s\t%.2f\n",e.id,e.name,e.dept,e.salary);
        flag=1;
        break;
        }
    }
    if(flag==0)
    {
      printf("Details not found\n");
    }
    fclose(fp);
}

void searchbyid()
{
    FILE *fp;
    struct employee e;
    int id,flag=0;

         fp=fopen("employee.dat","rb");
         if(fp==NULL)
     {
        printf("File cannot be opened");
        return ;
     }
     printf("Enter employee id to search=");
     scanf("%d",&id);

     printf("Id\tName\tDept\tsalary\n");
    while(fread(&e,sizeof(e),1,fp)==1)
    {
        if(e.id==id)
        {
         printf("%d\t%s\t%s\t%.2f\n",e.id,e.name,e.dept,e.salary);
        flag=1;
        break;
        }
    }

    if(flag==0)
    {
      printf("Details not found\n");
    }
    fclose(fp);
}

void searchbydeptname()
{
    FILE *fp;
    struct employee e;
    int flag=0;
    char name[50];

         fp=fopen("employee.dat","rb");
         printf("Enter employee dept_name to search=");
         scanf("%s",name);

         printf("Id\tName\tDept\tsalary\n");
    while(fread(&e,sizeof(e),1,fp)==1)
    {
        if(strcmp(e.dept , name)==0)
        {
        printf("%d\t%s\t%s\t%.2f\n",e.id,e.name,e.dept,e.salary);
        flag=1;
        break;
        }
    }

    if(flag==0)
    {
      printf("Details not found\n");
    }
    fclose(fp);
}

void searchbysalary()
{
    FILE *fp;
    struct employee e;
    int salary,flag=0;

         fp=fopen("employee.dat","rb");
         printf("Enter employee salary to search=");
         scanf("%d",&salary);

         printf("Id\tName\tDept\tsalary\n");
    while(fread(&e,sizeof(e),1,fp)==1)
    {
        if(e.salary==salary)
        {
        printf("%d\t%s\t%s\t%.2f\n",e.id,e.name,e.dept,e.salary);
        flag=1;
        break;
        }
    }
    if(flag==0)
    {
      printf("Details not found\n");
    }
    fclose(fp);

}

void update()
{
    FILE *fp,*fp1;
    int choice1,choice2=0,id;
    struct employee e;
    do
    {
    fp=fopen("employee.dat","rb");
    fp1=fopen("temp.dat","wb");

    if(fp==NULL || fp1==NULL)
    {
        printf("File not found");
        return;
    }

    printf("Enter id to update=");
    scanf("%d",&id);

    printf("1. Update name\n");
    printf("2. Update Dept_name\n");
    printf("3. Update salary\n");
    printf("Enter choice=");
    scanf("%d",&choice1);

        while(fread(&e,sizeof(e),1,fp)==1)
        {
            if(e.id==id)
            {
                switch(choice1)
                {
                    case 1:
                    printf("Enter new name=");
                    scanf("%s",e.name);
                    break;

                    case 2:
                    printf("Enter new dept_name=");
                    scanf("%s",e.dept);
                    break;

                    case 3:
                    printf("Enter new salary=");
                    scanf("%f",&e.salary);
                    break;
                }
            }
            fwrite(&e,sizeof(e),1,fp1);
        }
        fclose(fp);
        fclose(fp1);

   fp = fopen("employee.dat", "wb");
fp1 = fopen("temp.dat", "rb");

while(fread(&e,sizeof(e),1,fp1)==1)
{
    fwrite(&e,sizeof(e),1,fp);
}
fclose(fp);
fclose(fp1);

        printf("\nDo you continue(0-yes/ 1-no)=");
        scanf("%d",&choice2);
        } while (choice2==0);
}
int main()
{
    int n,uchoice,choice,dchoice,schoice;
    printf("Enter n=");
    scanf("%d",&n);

    do{

        printf("==========================Employee Management System=========================\n");
        
        printf("1. Input\n");
        printf("2. Display\n");
        printf("3. Searching option\n");
        printf("4. Sorting option\n");
        printf("5. Update option\n");
        printf("6. Delete option\n");

        printf("Enter choice=");
        scanf("%d",&uchoice);

      switch(uchoice)
      {
        case 1:
        input(n);
        break;

         case 2:
         display();
        break;

        case 3:
        printf("Searching option\n");

    printf("1. Search by id\n");
    printf("2.Search by name\n");
    printf("3. Search by dept name\n");
    printf("4. Search by salary\n");
    printf("Enter choice=");
       scanf("%d",&schoice);
       if(schoice==1)
       {
        searchbyid();
       }
       else if(schoice==2)
            {
            searchbyname();
            }
            else if(schoice==3)
            {
            searchbydeptname();
            }
            else if(schoice==4)
            {
            searchbysalary();
            }
        break;

        case 4:
    printf("Sorting option\n");

    printf("1. sort by id\n");
    printf("2. sort by name\n");
    printf("3. sort by dept name\n");
    printf("4. sort by salary\n");

       printf("Enter choice=");
       scanf("%d",&choice);

       if(choice==1)
       sortbyid();
       else if(choice==2)
           sortbyname();
        else if(choice==3)
            sortbydeptname();
            else if(choice==4)
            sortbysalary();
       display();
        break;

        case 5:
         update();
         display();
        break;

        case 6:
       printf("1. Delete by id\n");
       printf("2. Delete by name\n");
       printf("3. Delete by dept name\n");
       printf("4. Delete by salary\n");

        printf("Enter choice=");
        scanf("%d",&dchoice);
             if(dchoice==1)
                 deletebyid();
            else if(dchoice==2)
                 deletebyname();
              else if(dchoice==3)
                  deletebydeptname();
                  else if(dchoice==4)
                  deletebysalary();
        break;

        default:
        printf("Invalid choice\n");
      }
      
    }
   while(uchoice!=6);

    return 0;

}
