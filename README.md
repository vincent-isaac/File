# File

## Aim:
To Develop a C# program to get the values from the students such as name, age, department, and semester_percentage using the structure and store it in a file in a specific path using the file stream concept.

## Algorithm:
### step 1: 
Create a structure of student details.

### step 2:
Create a file using FileStream.

### step 3:
Get the number of students and their details from the user.

### step 4:
Create a function to write the details of the students in the created file.

### step 5:
Pass the details of the student to the function.

### step 6:
File has been created and written with student details.

<br/><br/><br/><br/><br/><br/>

## Program:
```c#
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.IO;
struct student
{
    public string name;
    public int age;
    public string dept;
    public float sem_percent;
};
public class program
{
    static void write(string name,int age,string dept,float percent,int i)
    {
            FileStream fs = new FileStream("file.txt", FileMode.Append, FileAccess.Write);
            StreamWriter sw = new StreamWriter(fs);
            sw.WriteLine("name of the student-{0}:{1}", i + 1, name);
            sw.WriteLine("age of the student-{0}:{1}", i + 1, age);
            sw.WriteLine("dept of the student-{0}:{1}", i + 1, dept);
            sw.WriteLine("semester percentage of the student-{0}:{1}", i + 1, percent);
            sw.WriteLine();
            sw.Close();
            fs.Close();
    }
    public static void Main(string[] args)
    {
        FileStream fs = new FileStream("file.txt", FileMode.Create, FileAccess.Write);
        fs.Close();
        Console.Write("Enter num of students:");
        int n = Convert.ToInt32(Console.ReadLine());
        student[] s = new student[n];
        for (int i = 0; i < n; i++)
        {
            Console.Write("Enter the name of the student-{0}:", i + 1);
            s[i].name = Console.ReadLine();
            Console.Write("Enter the age of the student-{0}:", i + 1);
            s[i].age = Convert.ToInt32(Console.ReadLine());
            Console.Write("Enter the dept of the student-{0}:", i + 1);
            s[i].dept = Console.ReadLine();
            Console.Write("Enter the semester percentage of the student-{0}:", i + 1);
            s[i].sem_percent = float.Parse(Console.ReadLine());
            write(s[i].name, s[i].age, s[i].dept, s[i].sem_percent,i);
            Console.WriteLine();
        }
        Console.ReadKey();
    }
}
```
## Output:
![image](https://user-images.githubusercontent.com/75235488/173843110-700f9e68-94ef-4648-8c33-84e348599af1.png)

## Result:
C# program to get student details using structure and storing it in a file in a specific path using the file stream concept is implemented successfully.
