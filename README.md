using System;

class Program
{
    static void Main()
    {
        try
        {
            Console.Write("Enter minNumber: ");
            int minNum = int.Parse(Console.ReadLine());

            Console.Write("Enter maxNumber: ");
            int maxNum = int.Parse(Console.ReadLine());

            if (minNum >= maxNum)
            {
                Console.WriteLine("Error: minNumber should be less than maxNumber.");
                return;
            }

            int range = maxNum - minNum + 1;
            int[] frequencyArray = new int[range];
            Random rand = new Random();

            for (int i = 0; i < 1000; i++)
            {
                int randomNum = rand.Next(minNum, maxNum + 1);
                frequencyArray[randomNum - minNum]++;
            }

            Console.WriteLine("Number | Frequency");
            for (int i = 0; i < range; i++)
            {
                Console.WriteLine($"{minNum + i} | {frequencyArray[i]}");
            }
        }
        catch (FormatException)
        {
            Console.WriteLine("Invalid input. Please enter valid integers.");
        }
    }
}
