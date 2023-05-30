using System;

public class HelloWorld
{
    public static void Main(string[] args)
    {
        Console.WriteLine("Enter x: ");
        int x = Convert.ToInt32(Console.ReadLine());
        
        Console.WriteLine("Enter eps: ");
        double e = Convert.ToDouble(Console.ReadLine());
        
        double y0;
        if (x > 1)
            y0 = x/3;
        else
            y0 = x * 3;
        
        double res = kor(x, e, y0);
        System.Console.WriteLine("Result:  " + res);
        
        
        static double kor (int x, double e, double y0)
        {
            double yi = 0.5 * (y0 + x/y0);
        
            if (Math.Abs(yi- y0) < e)
                return yi;
            else
                return kor(x, e, yi);
        }
    }
}
