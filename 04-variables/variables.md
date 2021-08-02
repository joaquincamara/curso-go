# Variables

Hola Mundo! en este video platicaremos sobre las variables en GO, veremos, las diferentes formas de declarar variables y su comportamiento.

Como mencionamos en el video anterior, Go es un lenguaje de tipado estatico, esto quiere decir que el tipo de datos dentro de nuestra variables es analizado durante el tiempo de compilacion y no durante el tiempo de ejecucion y que debemos especificar que tipo de dato contendra nuestra variable. Esto nos ayuda a tener una menor cantidad de errores en el programa.

```golang

  package main

  func main() {

/*Primero veremos las variables declaradas sin inicializacion:

Para esto utilizamos la palabra reservada "var" seguido del nombre de nuestra variable y por ultimo su tipo. Algo importante que debemos recordar cuando declaremos variables de esta forma, es que, tendran algo que en Go se conoce como valor cero, , mediante el valor cero, Go asegura que cada variable tenga un valor con el mismo tipo con el que fue definido la variable; en el caso de una variable del tipo int, el valor cero es 0, cero para floats, false para boleanos, "" para strings y nil para slices, pointers, maps, channels y functions.*/
      var num int
      fmt.Println(num) // 0


      var str  string = "Yo soy un string"
      fmt.Println(str) // Yo soy un string

      // Go tambien es capaz de inferir el tipo de valor que contrandra una variable unicamente
      // por su expresion, aunque algunos desarrolladores no lo concideran una bueba practica.
      var bln = true

      // Por ultimo, dentro de las funciones tenemos las declaraciones cortas
      // Las cuales pueden ser utilizadas para declarar e inicializar funciones variables locales.
      // Donde el tipo de la variable es determinada por la expresion.
      // A diferencia de la anterior esta es conciderada una buena practica.
      myFloat := 1.1416

  }
```

Bien, como se habran dado cuenta hasta ahora hemos declarado nuestras funciones dentro de la "funcion main", esto quiere decir que hemos declarado variables locales, esto es porque este tipo de variables son inicializadas y sus declaraciones encontradas durante el tiempo de ejecucion de la funcion en donde se encuentran.

De igual manera poder declarar funciones a nivel de paquete, las cuales, son declaradas fuera de las funciones y por lo tanto son inicializadas antes de que la funcion main inicie.

Como pueden ver, aplican las mismas reglas para declarar variables de nivel paquete, con exeception del metedo de declaracion corta el cual solo puede ser utlizado para declarar variables locales, es decir en funciones.

```golang

  package main


      var str string = "Yo soy un string"
      var num int
      var bln = true

  func main() {

      fmt.Println(str) // Yo soy un string
      fmt.Println(num) // 0
      fmt.Println(bln) // true

  }
```
