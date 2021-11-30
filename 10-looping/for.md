## For loop

Hola amantes del Gophers, en esta seccion aprenderemos sobre la sentencia "for" y las diferentes formas en la que la podemos utilizar para poder hacer diferentes tipos de loops en nuestros programas.

A diferencia de otros lenguajes de programacion como Javascript donde tenemos diferentes opciones para iterar y hacer loops como el map(), forEach() y el for, en Go solo tenemos la sentencia "for" para poder implementar un loop o iteracion, dependera de como lo implementemos para optener comportamientos diferentes.

Comencemos con el "for" tradicional, al igual que en la mayoria de lenguajes, un "for" en Go tiene:

1. Un estado inicial.
2. Una condicion, la cual es evaluada antes de cada iteracion.
3. Un estado final, el cual se ejecuta al final de cada iteracion.

A diferencia de otros lenguajes, estos 3 elementos tendrian que estar rodeados por parentesis pero en el caso de Go no, unicamente los braquets son necesarios para especificar el cuerpo de nuestro "for".

Al igual que en el "if", podemos utilizar una declaracion corta de variables para definir el estado inicial de nuestro "for". Estas variables podran ser utilizadas dentro del scope de nuestro "for".

Por ultimo, como es de esperarse, nuestro "for" se detendra cuando el resultado de la condicional sea "false".

```golang

func main() {
	//sum := 0
	for i := 0; i < 5; i++ {

		fmt.Println(i)
        //1
        //2
        //3
        //4
	}
}

```

Para los y las mas veteranas, se habran dado cuenta que no tenemos una seccion en el curso que hable sobre la sentencia "while", y esto es porque en Go, no tenemos una palabra reservada para poder utilizar dicha sentencia. Esto no significa que no podamos replicar su funcionamiento.

Si pensamos en como funciona la setencia "while", lo que hace, es que while o mientras cierta condicional sea verdadera se ejecutara cierto codigo, esto puede ser representado en un "for" en Go de la siguiente forma:

```golang

func main() {
	num := 1
	for num < 10 { // Mientras esta condicion sea verdadera
		num += num // Se ejecuta esta seccion
	}
	fmt.Println(num) // 16
}
```

Como vimos en el ejemplo anterior, los "for" en Go, si omitimos el estado inicial y el estado final dejando solo la condicion simularemos la sentencia "while". 

