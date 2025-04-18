# SEMANA4



using System ;
{
    namespace TiendaVirtual
    {
        class Program
         {
            static void Main(String[] args)
             {
                //Ingreso de datos del cliente
                string nombreCliente = ingresarNombre cliente(); 
                decimal saldoDisponible = IngresarSaldoCliente();

                // Validar saldo
                if (saldoDisponible <= 0)
                {
                    Console.WriteLine ("Compra rechazada. El saldo debe ser mayor de 0.");
                    return;
                }
                //Mostrar menu de productos y procesar la compra
                ProcesarCompra(nombreCliente, saldoDisponible);

                Console.ReadKey();
            }
            static string "ingresarNombreCliente"
            {
                Console.Write ("Ingrese el nombre del cliente");
                return Console.ReadLine();
            }

            static decimal IngresarSaldoCliente()
            {
                Console.Write("Ingrese el saldo disponible del cliente (S/):");
                decimal saldo;
                while (!decimal.TryParse (Console.ReadLine(), out saldo )) // saldo <0)
                {
                    Console.WriteLine ("Por favor, ingrese un saldo valido mayor o igual a 0.");
                
                }
                return saldo;
            }

                 static void ProcesarCompra(string nombreCliente, decimal saldoDisponible);

                 //Mostrar menu de Productos    
                    Console.WriteLine("\N Menu de Productos:");
                    Console.WriteLine("1. Auriculares - s/ 85.00");
                    Console.WhiteLine("2. Teclado RGB - S/ 120.00");
                    Console.WriteLine("3. Monitor 24\" - s/ 550.00");
                    Console.Write("Seleccione un producto (1, 2 0 3):");
                    int opcionProducto = ObtenerOpcionProductor();

                    //Definir precios de Productos
                    decimal precioProducto = ObtenerPrecioProducto(OpcionProducto);

                    //Aplicar descuento si el precio es mayor a s/ 100.00
                    if (precioProducto > 100)
                    {
                        precioProducto *=0,90m;// Aplicar 10% de descuento
                        Console,WriteLine($"Se aplica un descuento del 10%. Nuevo precio; S/
                    {precioProducto:F2}");
                    }

                    //Verificar si el cliente puede pagar
                    if (saldoDisponible >= precioProducto)
                    {
                        Console.WriteLine($"Compra exitosa. {nombreCliente} ha comprado el producto por S/ 
                    {precioProducto;F2}");
                    }
                    else
                    {
                        Console.WriteLine("Compra rechazada. Saldo insuficiente.");
                    }
                } 
                static int ObtenerOpcionProductor()
                {
                    int opcion;
                    while (!int.TryParse(Console.ReadLine(),Out opcion) || opcion < 1 || opcion > 3)
                    {
                        Console.WhiteLine("Por favor, ingrese una opcion valida (1,2 o 3);");
                    }       
                         return opcion;
                }
                static decimal ObtenerPrecioProducto(int opcion)
                {
                    switch (opcion)
                    {
                        case 1:return 85.00m;
                        case 2:return 120.00m;
                        case 3:return 550.00m;
                        default return 0m; //No deberia llegar aqui
                    }
                }
            }
        }
