## Interfaces

Ahoy! navegantes del internet, en esta seccion aprenderemos sobre las interfaces en Go, su importancia y la gran cantidad de implementaciones que podemos darles en nuestros programas para tener un codigo modularizado y mantenible.

En Go las interfaces son consideradas un tipo de dato, lo que nos permite expresar generalidades sobre el comportamiento de otros tipos de nuestro programa, en palabras sencillas, las interfaces nos permiten programar funciones que son altamente adaptables para diferentes situaciones simplemente porque no estan abligdas a cumplir detalles al momento de implementarlas. 

En los capitulos anteriores hemos aprendido sobre los diferentes tipo de datos en Go, este tipo de datos como los "int", "float" o slices, se les conoce como tipo de datos concretos esto es porque su tipo representa el valor y nos dice las implementaciones o operaciones que podemos hacer con estos datos, como sumar o restas en los "int" o realizar un "for - range" con un slice, a diferencia de estos datos concretos, las interfaces son de tipo abstracto, ya que, no representa la estructura o posibles implementaciones de sus valores, si no que unicamente nos dice los metodos de los valores. En palabras mas sencillas "Las interfaces son contratos que describen comportamiento no valores".

En el siguiente ejemplo veremos como es la sintaxis de una interfaz en Go, como habiamos dicho en Go las interfaces son un tipo de dato abstracto, por lo tanto, para escribir una inicamos con la palabra reservada "type", el nombre de nuestra interfaz, la palabra reservada "interface"., dentro del cuerpo de la interface tendremos los metodos, para definir un metodo, unicamente tenemos que escribir la firma de una funcion sin la palabra reservada "func", si nuestra funcion retorna un tipo de dato tenemos que especificarlo.

```golang

type Dog interface {
    Bark(dogName string) bark string // Arya woof woof 
    DogsName(dogName string) // Arya!
}
```


Algo interesante de la interfaces en Go, es que como los structs, las interfaces pueden embeberse entre ellas para modularizar sus funcionalidades.

En el siguiente ejemplo usaremos nuestra interfaz "Dog", y en ella tendremos las interfaz "Animal", la cual, nos data metodos con funciones basicas de un animal como: comer, caminar y dormir.

```golang

type Animal interface {
    Walk(animalName string) // Imprime Arya is walking!
    Eat(animalName string) // Imprime Arya is eating!
    Sleaping(animalName string) // Imprime Arya is sleeping!
}

type Dog interface {
    Bark(dogName string) bark string // Arya woof woof 
    DogsName(dogName string) // Arya!
    Animal // ahora tenemos todos los metodos de la interfaz Animal
}
```

Para muchos el uso de las interfaces puede parecer redundante, ya que a primera vista si puede interpretar que escribimos dos veces el metodo, una vez para la interfaz y otra vez en el struct que vaya a implementar el metodo, y esta percepcion normalmente sucede cuando queremos interpretar las interfaces como su fueran clases y no como  un conjunto de metedos.

un ejemplo claro son nuestras muestras anteriores, aunque es verdad que representan muy bien la funcionalidad de las interfaces aun se puede implementar de una forma mas aliniada a la filosofia de interfases en Go, hagamos un pequeño refactor a nuestras interfaces.

Bien, algo que siempre tenemos que tener en cuenta, es la regla de "mantener las interfaces lo mas simple posible", por lo tanto, tener una interfaz "Animal", con todos los metodos que representan el comportamiento de un animal, tendremos varias interfaces encargadas de describir un comportamiento.

```golang

type Walker interface {
    walk(animalName string) // Imprime: Arya is walking!
}

type Eater interface {
    eat(animalName string) // Imprime: Arya is eating!
}

type Sleeper interface {
    sleep(animalName string) // Imprime: Arya is sleeping!
}

```

Hasta ahorita todo bien, pero que hay de la interfaz "Dog", que implementa "Bark" and "DogName" ?, el problema con esta forma de implementar la interfaz, es que si, quisieramos crear una nueva interfaz que represente a un lobo, podriamos componer la interfaz "Dog", dentro de la interfaz "wolf", pero "wolf" tendria un metodo que no utilizaria "DogsName".

Ahora hagamos un refactor de la interfaz "Dog".

```Golang

type Barker interface {
    bark(animalName string) // Imprime: Arya is barking!
}

type Naming interface {
    name(animalName string) // Imrpime: Arya!
}
```
Ahora que tenemos una interfaz unica para el nombrado de los animales, ya no se encuntra atada a la interfaz "Dog", por lo tanto, podemos utilizarla para varios animales. Implementemos nuestras enterfaces:

```golang

type Barker interface {
	bark() // Imprime: Arya is barking!
}

type Wolf struct {
	Name string
}

func (w Wolf) bark() {
	fmt.Println(w.Name, "the wolf is barking")
}

type Dog struct {
	Name string
}

func (d Dog) bark() {
	fmt.Println(d.Name, "the dog is barking")
}

func main() {
	var nimeria Barker
	var arya Barker
	nimeria = Wolf{Name: "Nimeria"}
	arya = Dog{Name: "Arya"}
	nimeria.bark()
	arya.bark()

}

```

Como podemos ver usamos la interfaz Barker para implementar el mismo metodo en nuestros structs Dog y Wolf, de esta forma podemos usar de manera mas eficaz las interfaces, ya que podemos usar composicion junto con ellas a lo largo de nuestros programas.