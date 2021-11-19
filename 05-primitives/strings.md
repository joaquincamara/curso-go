# **Strings**

Hola de nuevo mis compañeros y compañeras desarrolladores, hasta ahora ya hemos visto la mayoria de los tipos de datos que podemos utilizar en Go, ahora, vamos a hablar sobre los strings y algunas de las principales aplicaciones que podemos hacer con este tipo de dato.

Al importante que tenemos que saber es que cualquier caracter UTF-8 es considerado un string en Go, esto caracteristica los hace realmente utiles y versatiles, pero de igual manera, quiere decir que no podemos utilizar todos los tipos de caracteres disponibles, pero no se preocupen, ya que Go nos da una solucion que veremos en otro tema. 

Primero hablaramos sobre una de las curiosidades de los strings, y se trata de, que al ser una cadena de caracteres podemos, hasta cierto punto, tratarla como un array, es decir que podemos acceder a los elementos especificos de un string, de la misma forma que lo hariamos con un array.

```golang

func main() {
    str := "Ahoy crew!"
    fmt.Println(str[1]) // 104
}
```

Se estaran preguntando, ¿Por qué se esta imprimiento 104 en lugar de ¨h¨?, bueno, esto es porque los strings en Go son realmente alias de bytes, pero podemos hacer una pequeña conversion para tener el resultado que estamos esperando. 

```golang

func main() {
    str := "Ahoy crew!"
    fmt.Println(string(str[1])) // h
}
```

Algo importante que debemos recordar sobre los strings, es que son inmutables, esto quiere decir que si intentamos modificar alguno de los elementos de un string Go nos arrojara un error.

```golang

func main() {
    str := "Ahoy crew!"
    str[1] = "x"
    fmt.Println(str) // cannot assign to s[1]
}
```

Bien por ultimo, asi como con los datos de tipo numero podemos realizar varias operaciones aritmeticas, con los string podemos realizar una de ellas, llamada concatenacion de strings, para esto utilizamos el operador "+" para "sumar" o mas bien unir dos strings diferentes.

```golang

func main() {
    str1 := "Ahoy"
    str2 := "capitan!"
    fmt.Println(str1 + str2) // Ahoycapitan!
}
```
