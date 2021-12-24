## Goroutines

Ahoy de nuevo nagavegantes del interntet, en este capitulo aprenderemos sobre uno de los mecanismos mas interesantes en Go, las cuales son, las goroutines, utilizadas para el desarrollo de software concurrente.

En terminos sencillos las "goroutines", son hilos o threads muy ligeros que son manejados por el tiempo de ejemcucion de Go. En conjunto con los channels, podemos realizar programacion concurrente. En Go, cuando un programa inicia, por default corre una "goroutine", la cual es, la funcion main(), que encontramos en todos los programas escritos en Go.

Para crear una nueva goroutine, es necesario utilizar la palabra reservada "go", antes de la ejecucion de una funcion:

```golang

func main() {
    go ahoy()
}

func ahoy() {
fmt.Println("Ahoy capitan")
}
```

En el ejemplo anterior vemos como la funcion "ahoy()", es ejecutada como una goroutine, algo interesante que sucede con este tipo de funciones es su implementacion concurrente. La concurrencia es el manejar varias cosas que pueden estar sucediendo al mismo tiempo, en nuestro ejemplo nosotros no tenemos control de la forma en la que se ejecuta la funcion, es decir en el siguiente caso, vemos que en la funcion main nuestras funciones ahoy, drunkenSailor y leaveHerJhonny son llamadas en este mismo orden, por lo tanto, deberiamos ver sus mensajes en ese mismo orden, pero debido a que las estamos ejecutando de manera concurrente el resultado podria ser diferente cada vez que ejecutemos el codigo.

```golang

func main() {
    go ahoy()
    go drunkenSailor()
    go leaveHerJhonny()
}

func ahoy() {
fmt.Println("Ahoy capitan")
}

func drunkenSailor() {
    fmt.Println("What we are going to do with the drunken sailor")
}

func leaveHerJhonny() {
    fmt.Println("oooh leave her, leave her Jhonny")
    
}
```

Para tener control sobre el tiempo de ejecucion de nustras goroutines utilizamos un tipo de dato llamado "channel", el cual veremos en el siguiente capitulo.