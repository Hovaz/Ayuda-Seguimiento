# Ayuda-Seguimiento
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace ejercicio_forma_1
{
    class Program
    {
        static void Main(string[] args)
        {
          bool menu = false;
          do
          {
              double precio, resultado;
              int zona;
              string datoa, datob;
              Console.WriteLine("Este programa le ayudara a conocer los costos de envio que debe cubrir en 4 zonas distintas \n");
              Console.WriteLine("Porfavor ingrese la zona a la cual quiere enviar el producto, tiene disponibles: 1,2,3,4");
              datoa = Console.ReadLine();
              Console.WriteLine("porfavor ingrese el valor del producto");
              datob = Console.ReadLine();
              Console.WriteLine();

              if (int.TryParse(datoa, out zona) && double.TryParse(datob, out precio))
              {
                  if (zona >= 5)
                  {
                      Console.WriteLine("la zona ingresada no existe");

                  }
                  if (zona <= 0)
                  {
                      Console.WriteLine("la zona ingresada no existe");

                  }
                  if (zona == 1)
                  {
                      resultado = (precio / 100) * 25;
                      Console.WriteLine("El costo de envio en la zona " + zona + "\nPara su producto es igual a: " + resultado);
                  }
                  if (zona == 2)
                  {
                      resultado = (precio / 100) * 12 + 25;
                      Console.WriteLine("El costo de envio en la zona " + zona + "\nPara su producto es igual a: " + resultado);
                  }
                  if (zona == 3)
                  {
                      resultado = (precio / 100) * 8;
                      Console.WriteLine("El costo de envio en la zona " + zona + "\nPara su producto es igual a: " + resultado);
                  }
                  if (zona == 4)
                  {
                      resultado = (precio / 100) * 4 + 25;
                      Console.WriteLine("El costo de envio en la zona " + zona + "\nPara su producto es igual a: " + resultado);
                  }


              }

              else { Console.WriteLine("Datos invalidos reiniciando el programa"); }

              string respuesta = Console.ReadLine();
              if (respuesta == "si")
              {
                  menu = true;
              }

              Console.ReadKey();



          } while (menu == false);
            
          }
            
    }
}
