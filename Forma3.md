using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace ejercicio_forma_3
{ 
    public delegate double Dzona(double precio);

    class Program
    {
        static void Main(string[] args)
        {
            bool menu = false;
            do
            {
                int zona;
                double precio;
                string dato1, dato2;
                Console.WriteLine("Ingrese el numero de la zona (de 1 a 4)");
                dato1 = Console.ReadLine();
                int.TryParse(dato1, out zona);
                Console.WriteLine("Ingrese el valor del producto");
                dato2 = Console.ReadLine();
                double.TryParse(dato2, out precio);

                if (zona == 1)
                {
                    Dzona a = zona1;
                    a(precio);

                }
                if (zona == 2)
                {
                    Dzona a = zona2;
                    a(precio);

                }
                if (zona == 3)
                {
                    Dzona a = zona3;
                    a(precio);

                }
                if (zona == 4)
                {
                    Dzona a = zona4;
                    a(precio);

                }
                Console.WriteLine("desea salir");
                string respuesta = Console.ReadLine();
                if (respuesta == "si") { menu = true; }
              
            } while (menu == false);


        }
        public static double zona1(double a)
        {
            Double resultado;
            resultado = (a / 100) * 25;
            Console.WriteLine("El valor de envio en la zona 1\nEs de "+resultado);
            return a;
        
        }
        public static double zona2(double a)
        {
            Double resultado;
            resultado = (a / 100) * 12 + 25;
            Console.WriteLine("El valor de envio en la zona 2\nEs de " + resultado);
            return a;

        }
        public static double zona3(double a)
        {
            Double resultado;
            resultado = (a / 100) * 8;
            Console.WriteLine("El valor de envio en la zona 3\nEs de " + resultado);
            return a;

        }
        public static double zona4(double a)
        {
            Double resultado;
            resultado = (a / 100) * 4 + 25;
            Console.WriteLine("El valor de envio en la zona 4\nEs de " + resultado);
            return a;

        }
       
    }

}
