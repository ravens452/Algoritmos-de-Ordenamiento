Algoritmos de ordenamiento

La entrada de todos estos algoritmos es una lista de números enteros. La lista podría estar ordenada, aunque generalmente no lo va a estar. Los números no van a ser secuenciales necesariamente, es decir, una lista podría ser [32, 5, 27].

El resultado siempre es es una lista que contiene los mismos números de la lista de entrada pero ordenados de menor a mayor.

INSERTION SORT

Este algoritmo recorre cada elemento de la lista y va creando una nueva lista ordenada insertando el elemento en la posición correcta.
Es muy eficiente si la lista ya está ordenada (o casi ordenada) pero su complejidad sigue siendo O(n^2).
Es deficiente en algunos casos.
En algunos casos es lento.

    Funcionamiento:

    1.- La comparacion se hara desde el segundo elemento de la lista al cual llamaremos i, a continuacion se verificara que i sea menor a su antecesor; de lo contrario, si la afirmacion es falsa, el 2 elemento ya esta ordenado.
    2.- i Tomara la posicion del siguiente de la lista y lo compara a a su antecesor y asi respectivamente.

    Algoritmo:

    paso 1: [Para cada pos. del arreglo]	For i <- 2 to N do
    paso 2: [Inicializa v y j]				    v <- a[i]
                                                j <- i.
    paso 3: [Compara v con los anteriores]		While a[j-1] > v AND j>1 do
    paso 4: [Recorre los datos mayores]			    Set a[j] <- a[j-1],
    paso 5: [Decrementa j]					    set j <- j-1.
    paso 5: [Inserta v en su posición]		    set a[j] <- v.
    paso 6: [Fin]					End.


SELECTION SORT

El metodo de ordenamiento por seleccion consiste en encontrar el menor de todos los elementos del arreglo e intercambiarlo con el que esta en la primera posicion. Luego el segundo mas pequeño, y así sucesivamente hasta ordenar todo el arreglo.

RADIXSORT

COUNTING SORT
MERGESORT

El método Quicksort divide la estructura en dos y ordena cada mitad recursivamente. El caso del MergeSort es el opuesto, es decir, en éste método de unen dos estructuras ordenadas para formar una sola ordenada correctamente.

Tiene la ventaja de que utiliza un tiempo proporcional a: n log (n), su desventaja radica en que se requiere de un espacio extra para el procedimiento.

Este tipo de ordenamiento es útil cuando se tiene una estructura ordenada y los nuevos datos a añadir se almacenan en una estructura temporal para después agregarlos a la estructura original de manera que vuelva a quedar ordenada.
Procedimiento MergeSort

/*recibe el arreglo a ordenar un índice l que indica el límite inferior del arreglo a ordenar y un índice r que indica el límite superior*/

void mergesort(int a[], int l, int r)
{
	int i,j,k,m,b[MAX];
	if (r > l) 
	{
		m = (r+l) /2;
		mergesort(a, l, m);
		mergesort(a, m+1, r);
		for (i= m+1; i > l;i--)
			b[i-1] = a[i-1];
		for (j= m; j < r;j++) 
			b[r+m-j] = a[j+1];
		for (k=l ; k <=r; k++)
			if(b[i] < b[j])
			   a[k] = b[i++];
			else
			   a[k] = b[j--];
	}
}

a = {a,s,o,r,t,i,n,g,e,x,a,m,p,l,e}
      {a,s,
            o,r,
       a,o,r,s,
                 i,t,
                     g,n,
                 g,i,n,t,
       a,g,i,n,o,r,s,t,
                          e,x,
                               a,m,
                          a,e,m,x,
                                     l,p,
                                     e,l,p}
                          a,e,e,l,m,p,x}

a = {a,a,e,e,g,i,l,m,n,o,p,r,s,t,x}


QUICKSORT

Es un método de ordenamiento recursivo y en lenguajes en dónde no se permite la recursividad esto puede causar un retraso significativo en la ejecución del quicksort.

Su tiempo de ejecución es de n log2n en promedio.


void quicksort(int a[], int l, int r)
{
	int i,j,v;
	if(r > l)
	{
		v = a[r];
		i = l-1;
		j = r;
		for(;;)
		{
			while(a[++i] < v && i < r);
			while(a[--j] > v && j > l);
			if( i >= j)
				break;
			swap(a,i,j);			
		}
		swap(a,i,r);
		quicksort(a,l,i-1);
		quicksort(a,i+1,r);
	}
}
a = {a,s,o,r,t,i,n}

a i o r t s n

a i n r t s o

a i n o t s r

a i n o r s t



Algoritmos de Ordenamiento
Volver a: Semana 4
investigar y analizar los siguientes algoritmos de ordenamiento:

insertionsort
selectionsort
radixsort
counting sort
mergesort
quicksort
Debe entregar un informe donde:

Explique detalladamente el funcionamiento del algoritmo.
Explique el tiempo de ejecución en el mejor y peor caso.
Colocar en anexo el código de cada algoritmo y adicionalmente el link hacia su repositorio donde debe estar el algoritmo.
SALUDOS.