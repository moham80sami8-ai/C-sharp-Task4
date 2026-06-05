using System;

namespace StudentApp { // A class is a blueprint for creating objects. // It defines properties (fields) and behaviors (methods). class Student { // Fields (variables inside the class) public string name; public int age; public double grade;

    // Constant (same value for all objects)
    public const string universityName = "Yarmouk University";

    // Static member (shared among all objects)
    public static int studentCount = 0;

    // Constructor (called when object is created)
    public Student(string name, int age, double grade)
    {
        this.name = name;
        this.age = age;
        this.grade = grade;

        studentCount++; // Increase count when a new student is created
    }

    // Method to display student information
    public void DisplayInfo()
    {
        Console.WriteLine("Name: " + name);
        Console.WriteLine("Age: " + age);
        Console.WriteLine("Grade: " + grade);
        Console.WriteLine("University: " + universityName);
    }

    // Method to update grade
    public void UpdateGrade(double newGrade)
    {
        grade = newGrade;
    }

    // Method to check if student passed
    public bool IsPassed()
    {
        return grade >= 50;
    }
}

class Program
{
    static void Main(string[] args)
    {
        // An object is an instance of a class.
        // Example: s1, s2, s3 are objects created from Student class.

        Student s1 = new Student("Anwar", 23, 75.5);
        Student s2 = new Student("Mohammad", 19, 45.0);
        Student s3 = new Student("Hassan", 21, 60.0);

        // Display info and pass status for each student
        Student[] students = { s1, s2, s3 };

        foreach (Student s in students)
        {
            s.DisplayInfo();

            if (s.IsPassed())
                Console.WriteLine("Status: Passed");
            else
                Console.WriteLine("Status: Failed");

            Console.WriteLine("----------------------");
        }

        // Update grade example
        s2.UpdateGrade(55);

        Console.WriteLine("After updating Lina's grade:");
        s2.DisplayInfo();
        Console.WriteLine("Status: " + (s2.IsPassed() ? "Passed" : "Failed"));

        Console.WriteLine("----------------------");

        // Display total number of students
        Console.WriteLine("Total Students Created: " + Student.studentCount);

            // 1. Even or Odd
            CheckEvenOdd(7);

            // 2. Second smallest
            int[] arr1 = { 4, -3, 7, 2, 0 };
            SecondSmallest(arr1);

            // 3. Factorial
            Factorial(5);

            // 5. Largest number in array
            int[] arr2 = { 3, 1, 4, 1, 5, 9 };
            FindLargest(arr2);

            // 6. Number pattern
            NumberPattern(5);

            // 7. Star pyramid (optional)
            StarPyramid(4);

            // 8. Sum of even & odd (optional)
            int[] arr3 = { 1, 2, 3, 4, 5, 6 };
            SumEvenOdd(arr3);

            // 9. Common elements (optional)
            int[] a = { 1, 2, 3, 4 };
            int[] b = { 3, 4, 5, 6 };
            CommonElements(a, b);
        }

        // 1. Even or Odd
        static void CheckEvenOdd(int number)
        {
            if (number % 2 == 0)
                Console.WriteLine($"The number {number} is even.");
            else
                Console.WriteLine($"The number {number} is odd.");
        }

        // 2. Second smallest number
        static void SecondSmallest(int[] arr)
        {
            Array.Sort(arr);
            Console.WriteLine("Second smallest: " + arr[1]);
        }

        // 3. Factorial using for loop
        static void Factorial(int n)
        {
            int result = 1;

            for (int i = 1; i <= n; i++)
            {
                result *= i;
            }

            Console.WriteLine($"Factorial of {n} = {result}");
        }

        // 5. Find largest using foreach
        static void FindLargest(int[] arr)
        {
            int max = arr[0];

            foreach (int num in arr)
            {
                if (num > max)
                    max = num;
            }

            Console.WriteLine("Largest number: " + max);
        }

        // 6. Number pattern
        static void NumberPattern(int n)
        {
            int num = 1;

            for (int i = 1; i <= n; i++)
            {
                for (int j = 1; j <= i; j++)
                {
                    Console.Write(num + " ");
                    num++;
                }
                Console.WriteLine();
            }
        }

        // 7. Star pyramid (optional)
        static void StarPyramid(int n)
        {
            for (int i = 1; i <= n; i++)
            {
                // spaces
                for (int j = 1; j <= n - i; j++)
                    Console.Write(" ");

                // stars
                for (int k = 1; k <= (2 * i - 1); k++)
                    Console.Write("*");

                Console.WriteLine();
            }
        }

        // 8. Sum of even and odd numbers
        static void SumEvenOdd(int[] arr)
        {
            int evenSum = 0, oddSum = 0;

            foreach (int num in arr)
            {
                if (num % 2 == 0)
                    evenSum += num;
                else
                    oddSum += num;
            }

            Console.WriteLine("Sum of Even Numbers: " + evenSum);
            Console.WriteLine("Sum of Odd Numbers: " + oddSum);
        }

        // 9. Common elements in two arrays
        static void CommonElements(int[] a, int[] b)
        {
            Console.Write("Common elements: ");

            foreach (int x in a)
            {
                foreach (int y in b)
                {
                    if (x == y)
                    {
                        Console.Write(x + " ");
                        break;
                    }
                }
            }

            Console.WriteLine();
        }
}
}
