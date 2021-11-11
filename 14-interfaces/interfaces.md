## Interfaces

Ahoy! navegantes del internet, en esta seccion aprenderemos sobre las interfaces en Go, su importancia y la gran cantidad de implementaciones que podemos darles en nuestros programas para tener un codigo modularizado y mantenible.

En Go las interfaces son consideradas un tipo de dato, lo que nos permite expresar generalidades sobre el comportamiento de otros tipos de nuestro programa, en palabras sencillas, las interfaces nos permiten programar funciones que son altamente adaptables para diferentes situaciones simplemente porque no estan abligdas a cumplir detalles al momento de implementarlas. 

En los capitulos anteriores hemos aprendido sobre los diferentes tipo de datos en Go, este tipo de datos como los "int", "float" o slices, se les conoce como tipo de datos concretos esto es porque su tipo representa el valor y nos dice las implementaciones o operaciones que podemos hacer con estos datos, como sumar o restas en los "int" o realizar un "for - range" con un slice, a diferencia de estos datos concretos, las interfaces son de tipo abstracto, ya que, no representa la estructura o posibles implementaciones de sus valores, si no que unicamente nos dice los metodos de los valores. En palabras mas sencillas "Las interfaces son contratos que describen comportamiento no valores".

En el siguiente ejemplo veremos como es la sintaxis de una interfaz en Go, como habiamos dicho en Go las interfaces son un tipo de dato abstracto, por lo tanto, para escribir una inicamos con la palabra reservada "type", el nombre de nuestra interfaz, la palabra reservada "interface"., dentro del cuerpo de la interface tendremos los metodos, para definir un metodo, unicamente tenemos que escribir la firma de una funcion sin la palabra reservada "func", si nuestra funcion retorna un tipo de dato tenemos que especificarlo.

```golang

type dogBehavior interface {
    Bark(dogName string) bark string // Arya woof woof 
    DogsName(dogName string) // Arya!
}
```


