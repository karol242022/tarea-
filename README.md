sing System;

namespace Thtomas
{
    class Program
    {
        stautic void Main(string[] args)
        {
            int opc;
            int buffer;
            int[] list = new int[8];
            opc = 0;
            do
            {
                Console.Clear();
                Console.WriteLine("MENU DE ARREGLOS UNIDIMENSIONALES");
                Console.WriteLine("1. Ingresar valores al arreglo");
                Console.WriteLine("2. Imprimir valores del arreglo");
                Console.WriteLine("3. Imprimir el valor mas alto del arreglo");
                Console.WriteLine("4. Imprimir el valor mas bajo del arreglo");
                Console.WriteLine("5. Imprimir la suma total del arreglo");
                Console.WriteLine("6. Imprimir el arreglo al reves");
                Console.WriteLine("7. Imprimiendo resumen de numeros pares y impares");
                Console.WriteLine("8. Imprimiendo el arreglo de numeros elevados al cuadrado");
                Console.WriteLine("9. Imprimiendo los numeros primos");
                Console.WriteLine("10. Salir");

                Console.WriteLine("Ingresar opcion del menu: ");
                opc = Convert.ToInt32(Console.ReadLine());

                switch (opc)
                {
                    case 1:
                        Console.WriteLine("Ingresando valores al arreglo");
                        for (int i = 0; i < list.Length; i++)
                        {
                            Console.WriteLine("Ingrese un numero para la posición " + i);
                            list[i] = Convert.ToInt32(Console.ReadLine());
                        }
                        Console.WriteLine("Proceso finalizado...");
                        break;
                    case 2:
                        Console.WriteLine("Imprimiendo valores del arreglo");
                        for (int i = 0; i < list.Length; i++)
                        {
                            Console.WriteLine("Posición [" + i + "]: " + list[i]);
                        }
                        break;
                    case 3:
                        Console.WriteLine("Imprimiendo el valor mas alto del arreglo");
                        buffer = 0;
                        for (int i = 0; i < list.Length; i++)
                        {
                            if (list[i] > buffer)
                            {
                                buffer = list[i];
                            }
                        }
                        Console.WriteLine("El numero mayor es: " + buffer);
                        break;
                    case 4:
                        Console.WriteLine("Imprimiendo el valor mas bajo del arreglo");
                        buffer = 0;
                        for (int i = 0; i < list.Length; i++)
                        {
                            if (i == 0)
                            {
                                buffer = list[i];
                            }
                            else
                            {
                                if (list[i] < buffer)
                                {
                                    buffer = list[i];
                                }
                            }
                        }
                        Console.WriteLine("El numero menor es: " + buffer);
                        break;
                    case 5:
                        Console.WriteLine("Imprimiendo la suma total del arreglo");
                        buffer = 0;
                        for (int i = 0; i < list.Length; i++)
                        {
                            buffer = buffer + list[i];
                        }
                        Console.WriteLine("La suma del arreglo es: " + buffer);
                        break;
                    case 6:
                        Console.WriteLine("Imprimiendo el arreglo al reves");
                        for (int i = list.Length - 1; i >= 0; i--)
                        {
                            Console.WriteLine("Posicion [" + i + "]:" + list[i]);
                        }
                        break;
                    case 7:
                        Console.WriteLine("Imprimiendo resumen de numeros pares y impares");
                        for (int i = 0; i < list.Length; i++)
                        {
                            if (list[i] % 2 == 0)
                            {
                              Console.WriteLine(" "+ list[i] + " Es un numero Par");
                            }
                            else
                            {
                                Console.WriteLine(" " + list[i] + " Es un numero Impar");
                            }                            
                        }
                        break;
                    case 8:
                        Console.WriteLine("Imprimiendo el arreglo de numeros elevados al cuadrado");
                        buffer = 0;
                        for (int i = 0; i < list.Length; i++)
                        {
                            buffer = list[i] * list[i];

                            Console.WriteLine("el numero elevado al cuadrado es " + buffer );
                        }
                        break;
                    case 9:
                        Console.WriteLine("Imprimiendo los numeros primos");
                        for (int i = 2; i < list.Length; i++)
                        {
                            
                                bool primo = true;

                                int max = i / 2;
                                for (int z = 2; z <= max; z++)
                                {
                                    if (i % z == 0) // Si es divisor, no es primo.
                                    {
                                        primo = false;
                                        break;
                                    }
                                }

                                if (primo) // Si es primo, lo saco por pantalla.
                                {
                                    Console.WriteLine(i +" si es un numero primo");
                                }                            
                        }
                        break;
                    case 10:
                        Console.WriteLine("Adios, gracias por usar el programa");
                        break;
                    default:
                        Console.WriteLine("Opps algo salio mal, ingrese una opcion de nuevo");
                        break;
                }
                Console.ReadKey();
            } while (opc != 7);
        }
    }
}
