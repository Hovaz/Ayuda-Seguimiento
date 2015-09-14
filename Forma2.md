using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace ejrcicio_forma_2
{
    class Program
    {
       
        static void Main(string[] args)
        {   bool menu = false;
        do
        {

            double precio;
            int zona;
            string dato1;
            string dato2;
            Console.WriteLine("Porfavor ingrese el numeor de la zona (de 1 a 4)");
            dato1 = Console.ReadLine();
            int.TryParse(dato1, out zona);
            Console.WriteLine("Porfavor ingrese el valor del producto");
            dato2 = Console.ReadLine();
            double.TryParse(dato2, out precio);


            if (zona == 1)
            {
                zona r = new zona1();
                r.impuesto(zona, precio);
            }
            if (zona == 2)
            {
                zona r = new zona2();
                r.impuesto(zona, precio);

            }
            if (zona == 3)
            {
                zona r = new zona4();
                r.impuesto(zona, precio);

            }
            if (zona == 4)
            {
                zona r = new zona4();
                r.impuesto(zona, precio);

            }

            Console.WriteLine("¿desea salir?");
            string respuesta = Console.ReadLine();
            if (respuesta == "si")
            {
                menu = true;
            }

        } while (menu == false);
        } 
    }
    public class zona
    {
        public double resultado { get; set; }
        public virtual void impuesto(int z, double p)
        {
            Console.WriteLine("El costo de envio en la zona "+z+"\nes de "+p);
        }
    }
    public class zona1 : zona
    {
        public override void impuesto(int z, double p)
        {
            resultado = (p / 100) * 25;
            base.impuesto(z, resultado);
            Console.ReadKey();
        } 
    }
    public class zona2 : zona
    {
        public override void impuesto(int z, double p)
        {
            resultado = (p / 100) * 12 +25;
            base.impuesto(z, resultado);
            Console.ReadKey();
        }
    }
    public class zona3 : zona
    {
        public override void impuesto(int z, double p)
        {
            resultado = (p / 100) * 8;
            base.impuesto(z, resultado);
            Console.ReadKey();
        }
    }
    public class zona4 : zona
    {
        public override void impuesto(int z, double p)
        {
            resultado = (p / 100) * 4 + 25;
            base.impuesto(z, resultado);
            Console.ReadKey();
        }
    }
}
