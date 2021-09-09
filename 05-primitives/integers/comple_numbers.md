## **Complex numbers**

Ahoy! mis compañeros desarrolladores, En la sección anterior platicamos floats, los cuales, son numeros que podemos escribir expresados de manera decimal, es decir, numeros como: 3.1416
Ahora veremos los numeros complejos o complex numbers en ingles, una de las principales ventajas de los numeros complejos en Go, es que son tratados como ciudadanos de primera clase, esto quiere decir, que los numeros complejos pueden ser usados en varias operaciones y casos en el lenguaje, como operaciones aritmeticas, pasarlos como parametros en las funciones y un gran etc.

Go no proporciona dos tipos de números complejos: complex64 y complex128, que corresponden a los tipos numericos float32 y float64 respectivamente, la razon de esto es porque tomamos un float64 mas un float64 para tener un complex128 y un float32 y float32  para crear un complex64, donde cada uno de los floats se divide en un numero real e imaginario

complex64 = float32: numero real + float32: numero imaginario
complex128 = float64: numero real + float64: numero imaginario

Para declarar el numero imaginario de un numero compleo, debemos utilizar la sintaxis literal "i", despues de escribir el numero que se utilizara como imaginario.

```golang

func main() {
    var num complex64 = 2 + 3i
    fmt.Println(num) // (2 + 3i)
}
```

Las operaciones aritmeticas que podemos realizar con numero complejos en Go son:

```golang

func main() {
    var num1 complex64 = 2 + 3i
    var num2 complex64 = 3 + 4i
    fmt.Println(num1 + num2) // (5+7i)
    fmt.Println(num1 - num2) // (-1-1i)
    fmt.Println(num1 * num2) // (-6+17i)
    fmt.Println(num1 / num2) // (0.72+0.04i)
}
```