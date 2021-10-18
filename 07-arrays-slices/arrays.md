# Arrays

Hola de nuevo mis queridos y queridas compañeras, en esta seccion aprenderemos sobre los arrays y las diversas formas en la que podemos implementarlos en nuestro sistema.

En Go tenemos unas estructuras de datos especiales llamadas escructuras compuestas, las cuales, son un una agrupacion de varios datos, los cuales, en el caso de los Arrays todos los datos son del mismo tipo.

Una de las caracteristicas que debemos siempre tener en cuenta con los Arrays es su longitud o length en ingles, el cual determina la cantidad de datos que contiene el array, en el caso de Go, la longitud de un array es parte del tipo del mismo, por lo tanto, su longitud no puede ser modificada.

Podemos decir que un arrays es [n]T, donde "n" es la longitud del arrays expresada en numeros y "T", es el tipo de los datos que tendra en Arrays. Como ya sabemos los arrays comienzan a contar sus elementos desde la posicion 0 en adelante, por lo tanto, el primer elemento de nuestro Array estara en la posicion 0 y el segundo en la posision 1 y asi sucesivamente con todos los elemento que nuestros arrays puedan tener.

```golang

func main() {
    var arr [2]int
	arr[0] = 1
	arr[1] = 2
	fmt.Println(arr) // [1 2]

}
```

Al igual que con las variables podemos utilizar la sintaxis corta de Go para declarar arrays, al igual que como lo hariamos con una variable, la diferencia es que tendriamos que asignar de manera manual los elementos del array al momento de su declaracion.

```golang

func main() {
    arr := [2]int{1, 2} 
	fmt.Println(arr) // [1 2]

}
```

Por ultimo en caso de que, decidamos declar la longitud del array por medio de la cantidad litiral de elementos podemos utilizar una elipsis "..." en lugar de epecificar la longitud del array. De esta forma el length del arrays es determinado por los elemento al momento de la declarion.

```golang

func main() {
    arr := [...]int{1, 2} 
	fmt.Println(arr) // [1 2]

}
```