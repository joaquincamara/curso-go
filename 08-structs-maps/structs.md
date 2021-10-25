## Structs

Hola de nuevo amantes de lo binario, en esta seccion aprenderemos sobre los structs, los cuales son unos de los tipos de datos mas versatiles y utilizados en los programas escritos con Go, principalmente debido, a que en conjunto con las interfaces, nos permiten imitar la programacion orientada a objetos entre otras implementaciones.

Lo primero que hay que considerar es que los structs son un tipo de dato definido por el usuario o desarrollador, dandonos la posibilidad de reunir varios tipos de datos en uno solo, por lo tanto, podemos utilizar los structs de Golang para representar entidades del mundo real.

```golang

func main() {
    type Dog struct {
        name string
        breed string
        age int32
    }
}
```

Bien, como comentamos, los structs son tipos de datos, por lo tanto no podemos utilizarlos como variables o constantes, para esto, tenemos que crear una variable y asignarle el tipo de dato el cual representa nuestro struct, como ya sabemos, en Go, tenemos diferentes formas de crear variables e igualmente tenemos varias opciones al crear variables y constantes basadas en structs.

En el siguiente ejemplo crearemos una variable del tipo "Dog", la cual, a no tener valores definidos toma el valor cero de cada uno de sus propiedades respectivamente, es decir, "name" y "breed" tendrian un string vacio y "age" tendria un valor de cero.

```golang

func main() {
    type Dog struct {
        name string
        breed string
        age int32
    }

    var chihuahua Dog
}
```

De igual forma podemos inicializar una variable por medio de una declaracion literal, es importante recordar que cuando declaramos una variable de esta forma, tenemos que declarar los valores de sus propiedades en el mismo orden que tienen en el struct.


```golang

func main() {
    type Dog struct {
        name string
        breed string
        age int32
    }

    var arya =  Dog{"Arya", "labrador", 1}
}
```

Por ultimo, Go tambien soporta la sintaxis de "name:value", las ventajas de esta sintaxis son que el orden no tiene relevancia y podemos seleccionar que propiedades inicializar y cuales no, las propiedades que no se inicialicen tendras su respectivo valor cero. 


```golang

func main() {
    type Dog struct {
        name string
        breed string
        age int32
    }

    var amy =  Dog{name:"Amy", breed: "bassedhound"}
    fmt.Println(amy) // {amy, bassedhound, 0} // age tiene el valor 0
}
```

Go nos permite utilizar el operador "." para poder acceder individualmente a los campos de nuestras variables basadas en structs.

```golang

func main() {
    type Dog struct {
        name string
        breed string
        age int32
    }

    var amy =  Dog{name:"Amy", breed: "bassedhound"}
    fmt.Println(amy.breed) // {bassedhound} 
}
```