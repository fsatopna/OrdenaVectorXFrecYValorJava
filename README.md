***
# OrdenaVectorXFrecYValorJava
***

Version que usa HashMap.

Tomado de: https://www.geeksforgeeks.org/sort-elements-by-frequency-set-5-using-java-map/

## Problema: 
Se tiene un vector de enteros, y se desea ordenar el mismo por la frecuencia de cada elemento y para la misma frecuencia por el valor del elemento:

* entrada:  {5, 1, 5, 4, 3, 5, 5, 3}    
* salida :  {1, 4, 3, 3, 5, 5, 5, 5} 

### Entrada
<Table>
  <tr>
      <td>Elementos</td>
      <td>5</td>
      <td>1</td>
      <td>5</td>
      <td>4</td>
      <td>3</td>
      <td>5</td>
      <td>5</td>
      <td>3</td>
   </tr>
   <tr>
</Table>

### Frecuencias
<Table>
  <tr>
      <td>Elemento</td>
      <td>1</td>
      <td>3</td>
      <td>4</td>
      <td>5</td>
   </tr>
   <tr>
    <td>Frecuencia</td>
      <td>1</td>
      <td>2</td>
      <td>1</td>
      <td>4</td>
  </tr>
</Table>

## Objetivo
Comprender y utilizar HashMap e interfaz sort para resolución de problemas de conjunto.

***


## Estrategia: 
* Crea Mapa (HashMap),  clave(elemento) y valor(frec)          `Map {1=1, 3=2, 4=1, 5=4}` 
* Ordenar el mapade pares {elemento, frecuencia}.   `           Map { 1 => 1, 4 => 1, 3 => 2, 5 => 4 }`


## Implementación: 
* ### Generar un Mapa (HashMap),  clave(elemento) y valor(frec)  .
```
        Map<Integer, Integer> map = new HashMap<>(); 
        List<Integer> res = new ArrayList<>();
        
  
        // Assign elements and their count in the list and map 
        for (int current : arr) { 
            int count = map.getOrDefault(current, 0); 
            map.put(current, count + 1); 
            res.add(current); 
        } 

```

* ### Ordenar el mapa de pares {elemento, frecuencia}.   .
```
        // (Compare the map by value) and (Sort the map using Collections CLass) 
        SortComparator comp = new SortComparator(map); 
        Collections.sort(res, comp); 

/*Clase */
// Implement Comparator Interface to sort the values 
class SortComparator implements Comparator<Integer> { 
    private final Map<Integer, Integer> freqMap; 
  
    // Assign the specified map 
    SortComparator(Map<Integer, Integer> tFreqMap) 
    { 
        this.freqMap = tFreqMap; 
    } 
  
    // Compare the values 
    @Override
    public int compare(Integer k1, Integer k2) 
    { 
  
        // Compare value by frequency 
        int freqCompare = freqMap.get(k1).compareTo(freqMap.get(k2)); 
  
        // Compare value if frequency is equal 
        int valueCompare = k1.compareTo(k2); 
  
        // If frequency is equal, then just compare by value, otherwise - 
        // compare by the frequency. 
        if (freqCompare == 0) 
            return valueCompare; 
        else
            return freqCompare; 
    } 
}

```

### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Alternativa de Ordenar el mapa de pares {elemento, frecuencia}.
```
    private static final boolean DEBUG = true;


```


