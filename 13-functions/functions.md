## Functions

Hola de nuevo navegantes del internet, hasta ahora hemos aprendido sobre los conceptos basicos de Go, desde como funcionan las variables, constantes y los diferentes tipos de datos que podemos utilizar en un programa escrito en Go, tambien hemos aprendido como modificar el estado de nuestros programas por medio de sentencias "if", "switch" y como podemos utilizar un "for" de diferentes formas.

Ahora veremos uno de los conceptos mas importantes en Go y en la mayoria de los lenguajes de progracion, en esta seccion aprenderemos sobre las funciones, su funcionamiento y las diferentes implementaciones que pueden tener con el lenguaje de programacion Go.

En Go tenemos la posibilidad de utilizar las funciones de diferenes formas, ya que se puede implementar closures, high-order functions, funciones literales y regresar mas de un valor. Esto le da una gran vesatilidad a las funciones, para declarar una fucion utilizamos la palabra reservada "func", seguido del nombre de la funcion, una lista de parametros rodeada de parentesis, el tipo de dato que retornara y el cuerpo de la funcion.

En el siguiente ejemplo tenemos una funcion llamada "sum", la cual recbide 2 parametros de tipo "int" y regresa un valor de tipo "int":0

```golang

func sum(num1 int, num2 int) int {
    return num1 + num2
}
```

si nuestra funcion regresa mas de un valor, la lista de valores que se regresan debe de ir rodeada de parentesis como la lista de parametros:

```golang

func lessThanTen(num int) (int, error) {

    if num > 10 {
        return 0, fmt.Error("num es mayor que 10")
    }

    return num, nil
    
}
```

En el ejemplo anterior, regresamos un "int" y un "error", los cuales, tienen su valor cero segun el caso.

De igual forma, una funcion puede no llevar parametros o valores de retorno:

```golang

func hello() {
    fmt.Println("Hola mundo!")
}

func printer(message string) {
    fmt.Println(message)
}
```

Hasta ahora hemos visto las diferentes formas en las que podemos declarar un funcion, ahora veremos la sintaxis que tenemos que seguir para invocarlas, la cual, como en la mayoria de los lenguajes es muy sencillo.

En siguiente ejemplo tenemos 2 funciones que seran llamadas dentro de la funcion "main" para ser utilizadas en nuestro programa.

```golang
func main() {
    message := "Yo soy el nuevo mensaje"
    hello() // imprime: Hola mundo!
    printer(message) // imprime: Yo soy el nuevo mensaje
}


func hello() {
    fmt.Println("Hola mundo!")
}

func printer(message string) {
    fmt.Println(message)
}
```

