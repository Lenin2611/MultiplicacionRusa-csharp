# Multiplicación Rusa

1. Desarrolle un programa que reciba como entrada el multiplicador y el multiplicando, y entregue como resultado el producto de ambos, calculado mediante el método de multiplicación rusa.

   ```c#
   while (true)
   {
   	bool loop = true;
   	int multiplicador = 0;
   	int multiplicando = 0;
   	List<int> listaMultiplicadores = new List<int>();
   	List<int> listaMultiplicandos = new List<int>();
   	List<int> listaImpar = new List<int>();
   	int suma = 0;
   	while (loop)
   	{
   		try
   		{
   			Console.Clear();
   			Console.Write("Ingrese multiplicador: ");
   			multiplicador = int.Parse(Console.ReadLine());
   			listaMultiplicadores.Add(multiplicador);
   			Console.Write("Ingrese multiplicando: ");
   			multiplicando = int.Parse(Console.ReadLine());
   			listaMultiplicandos.Add(multiplicando);
   			if (multiplicador % 2 != 0)
   			{
   				listaImpar.Add(multiplicando);
   			}
   			if (multiplicador > 0 && multiplicando > 0)
   			{
   				loop = false;
   			}
   			else
   			{
   				Console.Clear();
   				Console.Write("Error. . . ");
   				Console.ReadKey();
   			}
   		}
   		catch (Exception)
   		{
   			Console.Clear();
   			Console.Write("Error. . . ");
   			Console.ReadKey();
   		}
   	}
   	while (!listaMultiplicadores.Contains(1))
   	{
   		int ultimo = listaMultiplicadores.Count() - 1;
   		int division = (int)Math.Floor((decimal)listaMultiplicadores[ultimo] / 2);
   		listaMultiplicadores.Add(division);
   		int multiplicacion = listaMultiplicandos[ultimo] * 2;
   		listaMultiplicandos.Add(multiplicacion);
   		if (division % 2 != 0)
   		{
   			listaImpar.Add(multiplicacion);
   		}
   	}
   	foreach (int x in listaImpar)
   	{
   		suma += x;
   	}
   	Console.WriteLine($"Resultado: {suma}");
   	Console.Write("\nPresione Enter para volver. . . ");
   	Console.ReadKey();
   }
   ```

# 