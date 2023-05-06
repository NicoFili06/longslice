# longslice
- Data una stringa formata solo da cifre, calcolare il prodotto più grande per una sua sottostringa contigua di cifre di lunghezza N.

-Il codice inizia con due controlli di validità sui parametri "span" e "digits". Se "span" è uguale a zero, viene restituito 1 poiché il prodotto di zero cifre è 1. Se "span" è maggiore della lunghezza di "digits" o minore di zero, viene generata un'eccezione di tipo ArgumentException.
```c#
    public static long GetLargestProduct(string digits, int span)
{
    if (span == 0)
     {
        return 1;
    }
    if (span > digits.Length || span < 0)
    {
            throw new ArgumentException();
        }
```

-Successivamente, il codice utilizza un ciclo for per scorrere la stringa "digits" dall'inizio alla fine. Per ogni sottostringa di "span" cifre contigue, viene calcolato il prodotto delle cifre utilizzando un altro ciclo for. Il valore massimo del prodotto tra tutte le sottostringhe viene mantenuto in una variabile denominata "maxProduct"
```c#
        long maxProduct = 0;
        for (int i = 0; i <= digits.Length - span; i++)
        {
            long product = 1;
            for (int j = i; j < i + span; j++)
            {
                product *= digits[j] - '0';
            }
            if (product > maxProduct)
            {
                maxProduct = product;
            }
        }

```
-Infine, la funzione restituisce il valore di "maxProduct".

```c#
  return maxProduct;
    }
}
```
-codice completo
```c#
using System;
using System.Collections.Generic;
using System.Linq;

public static class LargestSeriesProduct

{
    public static long GetLargestProduct(string digits, int span)
{
    if (span == 0)
     {
        return 1;
    }
    if (span > digits.Length || span < 0)
    {
            throw new ArgumentException();
        }
        
        long maxProduct = 0;
        for (int i = 0; i <= digits.Length - span; i++)
        {
            long product = 1;
            for (int j = i; j < i + span; j++)
            {
                product *= digits[j] - '0';
            }
            if (product > maxProduct)
            {
                maxProduct = product;
            }
        }
        return maxProduct;
    }
}
```


