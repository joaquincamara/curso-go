# Constantes

Ahoy! mis compañeros desarrolladores, hasta ahora ya hemos visto los tipos de datos primitivos en Go y las diferentes aplicaciones que podemos darle a las variables que tienen datos primitivos, los cuales son parte fundamental en cualquier programa creado con el lenguaje de programcion Go.

En esta seccion veremos las constantes en el lenguaje de programcion Go y las diferentes aplicaciones que podemos darles en un programa escrito con este lenguaje.

Lo mas imporante que debemos recordar, es que en Go, los valores de las constantes no pueden ser cambiados despues de su asignacion

```golang

func main() {
    const myStr string = "I AM A CONSTANT STRING"
    myStr = "I WANT TO CHANAGE MY VALUE" // If we run this code we are going to have an error
}
```

Como sabemos, en algunos lenguajes existe la convecion de nombrar a las constantes en letras mayusculas separando las palabras que forman el nombre con un guin bajo, ejemplo: MY_CONSTANT, pero, debemos recordar que al escribir una variable o en este caso una constante, en la cual su nombre inicie con mayuscula el compilador de Go la exportara fuera del paquete donde fue declarada. Por lo tanto, la convencion para escribir constantes en Go, es la misma que usamos para las variables: "camelCase"

```golang

func main() {
    const camelCase string = "I AM A CONSTANT STRING NAMED CORRECTLY"
    const CAMEL_CASE string = "BAD" // constante publica y nombrada erroneamente //
}
```




Bien, ahora que ya aclaramos los estandares para el nombramiento de constantes en Go, podemos platicar sobre las constantes tipeadas, por fortuna, el proceso es practicamente igual al de crear variables tipeadas, la unica diferencia, es que en lugar de utilizar la palabra clave "var", usaremos la palabra clave "const".

```golang

func main() {
    const pi int32 = 3.1416
    const myString = "I am a string"
}
```

Asi como podran estar imaginando los valores de las constantes en Go no pueden ser modificados, por lo tanto realizar la siguiente accion nos producira un error:

```golang

func main() {
    const pi int32 = 3.1416
    pi = 100 // Esto producira un error al momento de correr el programa.
}
```