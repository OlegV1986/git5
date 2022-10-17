//задача 56



int[,] NewArray = new int[4, 4];
void NumberStringMinSumElements(int[,] array)
{
    int minString = 0;
    int minSumString = 0;
    int sumString = 0;
    for (int i = 0; i < NewArray.GetLength(1); i++)
    {
        minString += NewArray[0, i];
    }
    for (int i = 0; i < NewArray.GetLength(0); i++)
    {
        for (int j = 0; j < NewArray.GetLength(1); j++) sumString += NewArray[i, j];
        if (sumString < minString)
        {
            minString = sumString;
            minSumString = i;
        }
        sumString = 0;
    }
    Console.Write($"{minSumString + 1} строка");
    Console.WriteLine();
}
void PrintArray(int[,] array)
{
    for (int i = 0; i < array.GetLength(0); i++)
    {
        for (int j = 0; j < array.GetLength(1); j++)
        {
            Console.Write($"{array[i, j]} ");
        }
        Console.WriteLine();
    }
}
void FillArrayRandom(int[,] array)
{
    for (int i = 0; i < array.GetLength(0); i++)
    {
        for (int j = 0; j < array.GetLength(1); j++)
        {
            array[i, j] = new Random().Next(1, 10);
        }
    }
}
FillArrayRandom(NewArray);
PrintArray(NewArray);
Console.WriteLine();
NumberStringMinSumElements(NewArray);
