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

