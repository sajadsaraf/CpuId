using System;
using System.Management;

namespace ConsoleAppReview
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine($"Cpu id: {Machine.CpuId}\nMachine name: {Machine.ComputerName}");
            Console.ReadKey();
        }
    }
    public static class Machine
    {
        public static string CpuId
        {
            get
            {
                string? cpuInfo = null;
                ManagementClass managClass = new ManagementClass("win32_processor");
                ManagementObjectCollection managCollec = managClass.GetInstances();

                foreach (ManagementObject managObj in managCollec)
                {
                    cpuInfo = managObj.Properties["processorID"].Value.ToString();
                    break;
                }
                return cpuInfo.ToString();
            }
        }
        public static string ComputerName { get { return System.Environment.MachineName.ToString(); } }
    }
}
