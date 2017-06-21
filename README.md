using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace Grades
{
    class Program
    {
        static void Main(string[] args)
        {
            int students = int.Parse(Console.ReadLine());

            double lower = 0;
            double middle = 0;
            double good = 0;
            double excellent = 0;

            double totalGrades = 0;

            for (int i = 1; i <= students; i++)
            {
                double grades = double.Parse(Console.ReadLine());

                totalGrades += grades;

                if (grades < 3)
                {
                    lower++;
                }
                else if (grades < 4)
                {
                    middle++;
                }
                else if (grades < 5)
                {
                    good++;
                }
                else
                {
                    excellent++;
                }               
            }

            lower /= students;
            middle /= students;
            good /= students;
            excellent /= students;

            totalGrades /= students;

            Console.WriteLine("Top students: {0:f2}%", excellent * 100);
            Console.WriteLine("Between 4.00 and 4.99: {0:f2}%", good * 100);
            Console.WriteLine("Between 3.00 and 3.99: {0:f2}%", middle * 100);
            Console.WriteLine("Fail: {0:f2}%", lower * 100);
            Console.WriteLine("Average: {0:f2}", totalGrades);
        }
    }
}

