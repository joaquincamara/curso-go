## Pointers

Hola de nuevo querida y querido lector, en esta seccion aprenderemos sobre los "pointers", aunque pueden llegar a considerarse dificiles de entender o frustante para implementar, realmente son una herramienta bastante util e importante que nos permite optimizar nuestros programas.

Por definicion, un pointer es una variable que hace referencia a un espacio en memoria donde tenemos alojado un valor, esto quiere decir, que en lugar de leer el valor de nuestra variable tendremos la direccion de memoria en donde se encuentra dicho valor. Pero se estaran preguntando, ¿Por que pasar una direccion de memoria hace mas eficiente un programa?, realmente la respuesta es muy sencilla y principalmente es por dos razones, la primera, es que es mas "barato" pasar un "numero" (la direccion de memoria se representa por numeros), a diferencia de pasar un valor, el cual puede ser mas "largo" que la direccion de memoria.

Para la segunda razon imaginemos una situacion en donde a una funcion le pasamos una variable como parametro, debido al funcionamiento de Go, se creara una copia del parametro de la funcion para utilizarlo dentro de ella, ahora imaginemos esta situacion repetida en varias funciones y con parametros de gran tamaño, esto puede afectar directamete el rendimiento de nuestro programa. Pero si a la funcion le pasamos un pointer de la variable que usaremos como parametro, no se creara un copia del parametro dentro de la funcion, si no que, tendremos la posibilidad de acceder al valor que se aloja en la direccion de memoria de nuestro pointer.

En el siguiente ejemplo tenemos una funcion que recibe un string como parametro, el cual es asignado a la variable "str" y luego se imprime en consola, Go creara un copia del valor que fue enviado a la funcion para ser usado dentro de ella, cuando la funcion concluya su ejecucion, el recolector de basura del lenguaje se encargara de eliminar la copia que fue creada.

```golang

func main() {
    var initString = "Soy el valor original"
    myString(initString) // imprime: "soy el valor original"
}

func myString(str string) {
    fmt.Println(str)
}
```

Como dijimos antes, tener que copiar valores de diferente tamaño en varias funciones puede llegar a afectar el rendimiento de nuestro programa. Ahora intentemos lograr la misma funcionalidad pero con pointers. Para el lector mas veterano, podria decir que al usar pointers, imprimiriamos la direccion en memoria de la variable y no el valor que se aloja en ella, y es correcto, para indicar que una variable apunta a la direccion de memoria de un valor utilizamos el siguiente caracter "&" y para acceder al valor de la direccion en memoria utilizamos el caracter "*".

```golang

func main() {
    var initString = "Soy el valor original"
    myString(&initString)
}

func myString(str *string) {
    fmt.Println(*str) // imprime: el valor dentro de la direccion de memoria de la variable initString
    fmt.Println(str) //   imprimer: la direccion en memoria de la variable initString
}
```