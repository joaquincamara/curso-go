## **Complex numbers**

Ahoy! mis compañeros desarrolladores, En la sección anterior platicamos sobre los floats, los cuales, son numeros que podemos escribir expresados de manera decimal, es decir, numeros como: 3.1416
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

Bien, ahora ¿Que pasa si necesitamos acceder al numero real o imaginario de nuestro numero complejo?, para esto Go nos proporciona las funciones nativas real() e imag(), las cuales, aceptan por parametro un numero complejo y nos regresan la parte real o imaginaria segun como corresponda, es importante recordar que dependiendo si usamos un complex64 o un complex128 el resultado de las funciones real() e imag() sera un float32 o float64 segun corresponda al numero complejo que pasemos como parametro.

```golang

func main() {
    var num complex64 = 2 + 3i

    // Tipo float32
    fmt.Println(real(num)) // 2
    // Tipo float32
    fmt.Println(imag(num)) // 3
}
```

Por ultimo, si en algun punto de nuestra aplicacion necesitamos crear un numero complejo y no podemos acceder a la sintaxis literal "i", podemos utilizar la funcion nativa complex(), la cual acepta dos parametros, siendo el primer numero la parte real y el segundo la imaginaria de nuestro numero complejo.


```golang

func main() {
    var num complex64 = complex(2, 3)
    fmt.Println(num) // (2 + 3i)
}
```