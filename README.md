using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

//Первое задание

namespace draft
{
    internal class draft
    {
        static void Main(string[] args)
        {
            long N = 2000000000;
            double X = 2;

            // Измерение времени для первого решения
            DateTime start1 = DateTime.Now; //объявление переменной х типа double и присвание 2
            for (long i = 0; i < N; i++)
            {
                double z = Math.Pow(X, 2);
            }
            DateTime end1 = DateTime.Now; //текущее время в переменную
            TimeSpan duration1 = end1 - start1; //разница между текущем временем и переменной

            // Измерение времени для второго решения
            DateTime start2 = DateTime.Now;
            for (long i = 0; i < N; i++)
            {
                double z = X * X;
            }
            DateTime end2 = DateTime.Now;
            TimeSpan duration2 = end2 - start2;

            // Результат
            Console.WriteLine($"Время выполнения первого решения: {duration1.TotalMilliseconds} мс");
            Console.WriteLine($"Время выполнения второго решения: {duration2.TotalMilliseconds} мс");

            // Вычисление на скорость
            double fasterFactor = duration1.TotalMilliseconds / duration2.TotalMilliseconds;
            Console.WriteLine($"Умножение быстрее первого в {fasterFactor} раз.");

            Console.ReadKey();
        }
    }
}
