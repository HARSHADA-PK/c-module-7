# c-module-7
# EXP NO:1
C PROGRAM FOR ARRAY OF STRUCTURE TO CHECK ELIGIBILITY FOR THE VACCINE.

# Aim: 
To write a C program for array of structure to check eligibility for the vaccine person age above 18 years of age.

# Algorithm:

1.Declare structure eligible with age (integer) and n (character array)

2.Declare variable e of type eligible

3.Input age and name using scanf, store in a

4.If a.age <= 18

5.Print "eligibility: No" Else

6.Print "eligibility: Yes"

7.Print details (a.age, a.n)

8.Return 0

# Program:
```
#include<stdio.h>
struct eligibility
{
    int age;
    char name[20];
}a;
int main()
{
    scanf("%d",&a.age);
    scanf("%s",a.name);
    printf("Age:%d\n",a.age);
    printf("Name:%s",a.name);
    printf("vaccine:%d",a.age);
    if(a.age>18)
    {
        printf("\neligibility:yes");
    }
    else
    {
        printf("\neligibility:no");
    }
    return 0;
}
```

Output:

![image](https://github.com/user-attachments/assets/696ea8bc-04b0-4cb8-b0df-437a61dfa0f7)


Result: Thus, the program is verified successfully.

# EXP NO:2 
C PROGRAM FOR PASSING STRUCTURES AS FUNCTION ARGUMENTS AND RETURNING A STRUCTURE FROM A FUNCTION
# Aim: 
To write a C program for passing structure as function and returning a structure from a function

# Algorithm:

1.Define structure numbers with members a and b.

2.Declare variable n of type numbers.

3.Prompt the user to enter values for a and b.

4.Input values for a and b into n using scanf.

5.Call the add function with n as an argument.

6.Print the result returned by the add function.

7.Return 0
# Program:
```
#include <stdio.h>
struct Result {
    int sum;
};
struct Result calculate(int a, int b) {
    struct Result res;
    res.sum = a + b;
    return res; // Returning structure
}

int main() {
    int num1, num2;
    scanf("%d %d", &num1, &num2);
    struct Result result = calculate(num1, num2);
    printf("%d\n", result.sum);

    return 0;
}

```

# Output:

![image](https://github.com/user-attachments/assets/891cac93-285e-4771-813f-06491da52299)


Result: Thus, the program is verified successfully

# EXP.NO:3 
C PROGRAM TO READ A FILE NAME FROM USER AND WRITE THAT FILE USING FOPEN()

# Aim: 
To write a C program to read a file name from user

# Algorithm:

1.Include the necessary header file stdio.h.

2.Begin the main function.

3.Declare a file pointer p. Declare a character array name to store the file name.

4.Prompt the user to enter a file name. Use scanf to input the file name into the name array.

5.Print a message indicating that the file with the specified name has been created successfully.

6.Use fopen to open a file with the name provided by the user in write mode ("w").

7.If successful, continue to the next step.

8.If unsuccessful, print an error message and exit the program with a non-zero status.

9.Print a message indicating that the file has been opened successfully.

10.Use fclose to close the file.

11.Print a message indicating that the file has been closed.

12.End the main function.

13.Return 0 to indicate successful program execution.

# Program:
```
#include <stdio.h>
int main()
{
    char filename[50];
    scanf("%s",filename);
    FILE*file=fopen("filename","w");
    if(file==NULL)
    {
        printf("error");
        return 1;
    }
    printf("%s File Created Successfully\n",filename);
    printf("%s File Opened\n",filename);
    fclose(file);
    printf("%s File Closed",filename);
    return 0;
}
```
# Output:

![image](https://github.com/user-attachments/assets/5efcdbf7-c249-4397-abd2-30fb383ec1e8)


Result: Thus, the program is verified successfully

# EXP NO:4 
PROGRAM TO READ A FILE NAME FROM USER, WRITE THAT FILE AND INSERT TEXT IN TO THAT FILE
# Aim: 
To write a C program to read, a file and insert text in that file
# Algorithm:

1.Include the necessary header file stdio.h.

2.Begin the main function.

3.Declare a file pointer p. Declare character arrays name and text. Declare an integer variable num.

4.Prompt the user to enter a file name and the number of strings. Use scanf to input the file name into the name array and the number of strings into the num variable.

5.Use fopen to open a file with the name provided by the user in write mode ("w").

6.If successful, continue to the next step.

7.If unsuccessful, print an error message and exit the program with a non-zero status.

8.Print a message indicating that the file has been opened successfully.

9.Use a loop to input strings from the user and write them to the file using fputs.

10.Use fclose to close the file.

11.Print a message indicating that data has been added successfully.

12.End the main function.

13.Return 0 to indicate successful program execution.
# Program:
```
#include <stdio.h>
int main()
{
    char filename[50];
    int n,i;
    char text[50];
    scanf("%s",filename);
    FILE*file=fopen("filename","w");
    if(file==NULL)
    {
        printf("error");
        return 1;
    }
    printf("%s Opened\n",filename);
    scanf("%d",&n);
    for(i=0;i<n;i++)
    
    {
        scanf("%s",text);
        fprintf(file,"%s\n",text);
    }
    fclose(file);
    printf("Data added Successfully");
}
```
# Output:

![image](https://github.com/user-attachments/assets/b082738c-30dc-4f4b-937c-6d898cc7db18)

Result: Thus, the program is verified successfully

# Ex No 5 :
C PROGRAM TO DISPLAY STUDENT DETAILS USING STRUCTURE

# Aim:
The aim of this program is to dynamically allocate memory to store information about multiple subjects (name and marks), input the details for each subject, and then display the stored information. Finally, it frees the allocated memory to prevent memory leaks.

# Algorithm:
1.Input the number of subjects.

2.Read the integer value n from the user, which represents the number of subjects.

3.Dynamically allocate memory:

4.Use malloc to allocate memory for n subjects. Each subject has a name (array of characters) and marks (integer).

5.If memory allocation fails (i.e., the pointer s is NULL), display an error message and exit the program.

6.Input the details of each subject

7.Use a for loop to read the name and marks of each subject using scanf. For each subject, store the name as a string and marks as an integer in the dynamically allocated memory.

8.Display the details of each subject

9.Use another for loop to print the name and marks of each subject.

10.Free the allocated memory

11.After all operations are done, call free(s) to release the dynamically allocated memory.

12.Return from the main function

13.End the program by returning 0.

# Program:
```
#include <stdio.h>
#include <stdlib.h>
struct Subject
{
    char name[20];
    int marks;
};
int main()
{
    int i,n;
    scanf("%d",&n);
    struct Subject *s = (struct Subject *)malloc(n*sizeof(struct Subject));
    if(s==NULL)
    {
        printf("Memory Alocation Failed\n");
        return 1;
    }
    for(i=0;i<n;i++)
    {
        scanf("%s %d",s[i].name,&s[i].marks);
    }
    for(i=0;i<n;i++)
    {
        printf("%s  %d\n",s[i].name,s[i].marks);
    }
    
    free (s);
    
    return 0;
}
```
Output:

![image](https://github.com/user-attachments/assets/d86b06f4-f834-45de-a82f-0fa1743144cf)


Result: Thus, the program is verified successfully
