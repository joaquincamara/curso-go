## Slices

Ahoy, mi hermanas y hermanos del desarrollo de software, en el segmento anterior hablamos sobre los arrays, los cuales son un conjunto limitado de datos del mismo tipo ordenados por medio de indexes con una longitud no editabel, al tener una longitud fija los arrays se pueden considerar como elementos no muy utiles para ser utilizados en un sistema, pero, nuestros amigos y amigas del equipo Go crearon los Slices, los cuales, a diferencia de los arrays tienen una logintud que puede ser modificada a lo largo de su implementacion.

En terminos simples los slices son un conjunto de elementos del mismo tipo con una logintud variable, lo que nos permite incrementar o disminuir la cantidad de elementos dentro de un slice.

Podemos crear un slice de diferentes maneras segun las necesidades de nuestro sistema o estilo de programacion., entre las mas comunes son las siguienes:

El metodo integrado make(), el cual acepta el typo de dato que crearemos y su longitud como parametros

```golang

func main() {
    arr := make([]int32, 2)
    arr[0] = 1
    arr[1] = 2
    fmt.Println(arr) // [1, 2]
}
```

De igual forma podemos declarar e inicializar un slice en una sola linea: 

```golang

func main() {
    arr := []string{"J", "C", "R"}
    fmt.Println(arr) // [J, C, R]
}
```

Otra de las capacidades de lo slices , es que, en comparacion con los arrays, se pueden utilizar con un mayor rango de metodos, uno de los mas utilizados es el metodo integrado append(), el cual acepta un slice y el resto de los elementos que se agregaran al slice como parametros, este metodo nos regresara un nuevo slice con los valores el que utilizamos como parametros con los demas valores que pasamos como parametros. 


```golang

func main() {
    arr1 := make([]int32, 2)
    arr1[0] = 1
    arr1[1] = 2

    arr1 = append(arr1, 3, 4)
    fmt.Println(arr1)

}

```

Otro metodo que podemos utilizar con los slices es len(), el cual acepta como parametro un slice y nos regresara la longitud del slice que pasamos como parametro.

```golang

func main() {
    arr1 := make([]int32, 2)
    arr1[0] = 1
    arr1[1] = 2

    fmt.Println(len(arr1)) // 2

}

```

Por ultimo al igual que con los arrays podemos utilizar un "range" para iterar por cada uno de los elementos del array.

```golang

func main() {
    arr1 := make([]int32, 2)
    arr1[0] = 1
    arr1[1] = 2

    for _, v := range arr1 {
        fmt.Println(v)
    }

    // output: 1
    // output: 2

}
