## Maps 

Una de las estructuras de datos más útiles en informática es la tabla hash. Existen muchas implementaciones de tablas hash con diferentes propiedades, pero en general ofrecen búsquedas, adiciones y eliminaciones rápidas. Go proporciona un tipo de mapa integrado que implementa una tabla hash.

CITA: Andrew Gerrand, The Go Block, Go maps in action,  https://go.dev/blog/maps

Como Andrew Gerrand menciona, las tablas hash son estructura de datos que implementa una tabla hash, esto quiere decir que, asocia llaves o claves con valores y la La operación principal que soporta de manera eficiente es la búsqueda, permitiendo el acceso a los elementos almacenados a partir de una clave o llave generada.

por lo tanto se podemos decir que un mapa se representa de la siguiente forma: map[KeyType]ValueType

Los mapas realizan referencias, como los punteros, por lo que el valor de un mapa creada mediante la declaracion de una variable con la palabra clave "var", tendra un valor nulo, ya que, no apunta a un mapa inicializado. Un mapa nulo se comporta como un mapa vacío cuando se lee, pero los intentos de escribir en un mapa nulo provocarán un panic durante tiempo de ejecución. Para inicializar un mapa se utiliza la funcion integrada "make()".

En el siguiente ejemplo podemos ver que tenemos una variable llamada "week", la cual, es un map que tendra los nombres de la semana como llaves y el numero que le corresponde en la semana como su valor.

```golang

func main() {

    // Lunes - 1
    // Martes - 2
    // Miercoles - 3
    // ...
    var week map[string]int3 // provocara un panic


     week := make(map[string]int3) // Si se lee, tendremos un mapa vacio sin causar un panic
}
```

Para asignar valores a nuestro map  indicaremos la llave que se asiganara a un valor en especifico segun el tipo de dato que le corresponda a la llave y al valor, si tomamos el ejemplo anterior, el primer valor de nuestro mapa seria el numero "1" y tendria asigando la palabra "Lunes" como llave, el segundo valor seria "2" con la palabra "Martes" como llave y asi sucesivamente hasta cubrir todo los dias de la semana.

```golang

func main() {

    // Lunes - 1
    // Martes - 2
    // Miercoles - 3
    // ...
    week := make(map[string]int3)
    week["Lunes"] = 1
    week["Martes"] = 2
    week["Miercoles"] = 3
    // ...
}
```

Si queremos acceder a alguno de los valores de nuestro map, lo haremos por medio de la llave que le corresponde.

```golang

func main() {

    // Lunes - 1
    // Martes - 2
    // Miercoles - 3
    // ...
    week := make(map[string]int3)
    week["Lunes"] = 1
    week["Martes"] = 2
    week["Miercoles"] = 3
    // ...

    fmt.Println(week["Lunes"]) // 1
}

```

Podemos comprobar si una llave existe o de dos formas, la primera leyendo si el valor que retorna la llave es igual al valor cero del tipo de dato que hace referencia, por lo tanto, si quisieramos leer la llave "Abril" en nuestra mapa "week", tendriamos un "0", ya que este es el valor cero de los int32.

```golang

func main() {

    // Lunes - 1
    // Martes - 2
    // Miercoles - 3
    // ...
    week := make(map[string]int3)
    week["Lunes"] = 1
    week["Martes"] = 2
    week["Miercoles"] = 3
    // ...
    fmt.Println(week["Abril"]) // 0
}

```
En la segunda forma utilizaremos 2 asignaciones a la llave de nuestro mapa, la primera variable tendra asignado el valor al que haga referencia nuestra llave, si la llave no existe tendra el valor cero del tipo de dato al que haga referencia nuestra llave. La segunda variable tendra asignado false si la llave no existe y true si existe.

```golang

func main() {

    // Lunes - 1
    // Martes - 2
    // Miercoles - 3
    // ...
    week := make(map[string]int3)
    week["Lunes"] = 1
    week["Martes"] = 2
    week["Miercoles"] = 3
    // ...

    vf, okf := week["Abril"]
    fmt.Println(vf, okf) // 0 false

    vt, okt := week["Martes"]
    fmt.Println(vt, okt) // 2 true
}

```

Si queremos eliminar algun valor y la llave que le haga referencia dentro de nuestro map, pedemos utilizar la funcion integrada "delete()", la cual acepta dos parametros, el primero es nuestro map y el segundo el nombre de la llave que queremos eliminar.


```golang

func main() {

    // Lunes - 1
    // Martes - 2
    // Miercoles - 3
    // ...
    week := make(map[string]int3)
    week["Lunes"] = 1
    week["Martes"] = 2
    week["Miercoles"] = 3
    // ...

    delete(week, "Martes")

    v, ok := week["Martes"]
    fmt.Println(v, ok) // 0 false
}

```

Por ultimo, tenemos que mencionar que en Go, es posible iterar los valores de un map por medio de un "range"

```golang

func main() {

    // Lunes - 1
    // Martes - 2
    // Miercoles - 3
    // ...
    week := make(map[string]int3)
    week["Lunes"] = 1
    week["Martes"] = 2
    week["Miercoles"] = 3
    // ...

    for key, value := range week {
        fmt.Println(key, value) // Lunes 1, Marter 2, Miercores 3, ...
    }
}

```