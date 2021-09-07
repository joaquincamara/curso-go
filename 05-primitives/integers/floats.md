## **Floats:**

Los floats son un tipo de numero especial en Go que nos permiten utilizar numeros con el punto decimal, esto nos permite realizar operaciones artimeticas con resultados mas complejos. En Go los floats siguen el estandar IEEE 754, el cual es implementado por todas las CPUs modernas, dentro de este estandar podremos encontrar 2 tamaños diferentes: float32 y float64 bits.

- float32: 1.4e-45 hasta 3.4e38
- float64: 4.9e-324 hasta 1.8e308

```golang
	var x float32 = 10.32

    var y float64 = 11.234
    yx := 12.234 // Siempre sera float64

```

Al igual que con los tipos numericos "int" con los floats tenemos la posibilidad de realizar las siguientes operaciones aritmeticas:

```golang

func main() {
    x = 10.05
    y = 3.05
    
    fmt.Println(x + y) // 13.1
    fmt.Println(x - y) // 7
    fmt.Println(x * y) // 30.6525
    fmt.Println(x / y) // 3.4426
}
```