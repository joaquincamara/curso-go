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

Como sabemos, en algunos lenguajes existe la convecion de nombrar a las constantes en letras mayusculas separando las palabras que forman el nombre con un guin bajo, ejemplo: MY_CONSTANT, pero, debemos recordar que al escribir una variable o en este caso una constante, en la cual su nombre inicie con mayuscula el compilador de Go la hara publica. 

