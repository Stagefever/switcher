# switcher
text file read and edit test
using System;
using System.IO;


namespace switcher
{
    class Program
    {
        static void Main(string[] args)
        {
            string path = @"E:\global.sim";
            string text = File.ReadAllText(path);

            if(text.Contains("IGNITION	=ON"))
            {
                text = text.Replace("IGNITION	=ON", "IGNITION	=OFF");
                Console.WriteLine("Ignition OFF");
            }
            else if (text.Contains("IGNITION	=OFF"))
            {
                text = text.Replace("IGNITION	=OFF", "IGNITION	=ON");
                Console.WriteLine("Ignition ON");
            }
            else
            {
                Console.WriteLine("Nothing to Switch - check if file is there");
            }
                       
            File.WriteAllText(path, text);
        }
    }
}
