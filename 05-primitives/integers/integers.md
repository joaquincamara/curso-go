# Integers

Hola mundo! En este video hablaremos sobre las estructuras de datos basicas de Go, tambien conocidas como primitivos, hablaremos sobre su comportamiento y las diferentes operaciones que podemos realizar con cada uno de ellos. Comencemos!

En videos anteriores platicamos que Go es un lenguaje fuertemente tipado, lo que nos obliga a especificar el tipo de dato que alojamos en nuestras variables. Otra de las concecuencias postivas de esta caracteristica, es que tendremos varios tipos de "integers" int, floating point y complex.

## **int:**

Go nos permite trabajar con dos tipos de intergers los cuales son signed o unsigned. Los signed integers son los tipos de datos numeros que pueden contar con un simbolo - o +, por ejemplo: -3 o 2, tambien especifican el rango de los nuemores que podemos acceder desde el numero negativo al positivo, en Go tenemos cuatro: int8, int16, int32 e int64, con los siguientes rangos:

- int8: -128 a 127
- int16: -32 768 a 32 767
- int32: -2 147 483 648 a 2 147 483 647
- int64: -9 223 372 036 854 775 808 a 9 223 372 036 854 775 807

Cuando declaremos una varaible de esta forma:

```golang   

func main() {
    num := 42
    fmt.Println("%v, %T\n", num, num) // 42, int = 42int32
}
```
No estamos especificando si es un signed integer o no, por lo tanto, el compilador de Go por default lo declara como int32 auqnue esto puede variar segun el sistema operativo en el que estes desarrolando.

Bien ahora hablemos un poco sobre los unsigned interger, al contrario de los signed interfer, este tipo de numeros no cuenta con un rango de numeros negativos, es decir, que el rango inicia desde cero y es limitado segun el tamaño del tipo de dato, en Go tenemos tres: uint8, uint16 y uint32, con los siguientes rangos:

- uint8:  0 a 255
- uint16: 0 a 535
- uint32: 0 a 4 294 967 295

```golang

func main() {
    var num uint16 = 42
    fmt.Println("%v, %T\n", num, num) // 42, uint16
}
```

Ahora que sabemos estas diferencias podemos hablar sobre las operaciones aritmeticas construidas dentro de Go que podemos realizar con ellos:

```golang

func main() {
    x = 10
    y = 3
    
    fmt.Println(x + y) // 13
    fmt.Println(x - y) // 7
    fmt.Println(x * y) // 30
    fmt.Println(x / y) // 3
    fmt.Println(x % y) // 1
}
```

Si corremos el codig, podremos ver los resultados esperados en cada una de las operaciones, menos en una, x / y, nosotros sabemos que el resultado deberia de ser algo cercano a 3.333 pero como hemos platicado antes Go es un lenguaje fuertemente tipado, por lo tanto, para este caso no tendremos el resultado con numeros decimales, si no que Go se encargara de redondear el numero para que cumpla con el tipo de dato de la variable.

Si ejecutamos este codigo:

```golang

func main() {
	var x float32 = 10
	var y float32 = 3
	fmt.Println(x / y) // 3.3333333
}
```
El resultado sera el esperado para division.

Otra cosa importante es que no podemos realizar operaciones aritmeticas entre diferentes tipo de integers por ejemplo: 

```golang

func main() {
	var x float32 = 10
	var y int = 3
	fmt.Println(x + y) // Error!
}
```

Generara un error.

## **Floats:**

Los floats son un tipo de numero especial en Go que nos permiten utilizar numeros con el punto decimal.
