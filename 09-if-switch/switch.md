## Switch

Ahora que ya conocemos sobre las implementaciones de la sentencia "if", podemos hablar sobre la sentencia "switch", la cual podemos decir que es una forma corta de representar una sentencia "if - else", ya que podemos evaluar varios casos en un mismo switch. 

En sintaxis el switch de Go es parecido a los de C, Java y Javascript, pero con la exepcion, de que en Go, solo se corre el caso seleccionado y no todos los casos que le siguen, Esto es porque en otros lenguajes es necesario utilizar la palabra reservada "break" para poder evitar que se ejecuten todos los caso, pero en Go esta integrado automaticamente.

Debemos recordar que el orden de evaluacion de los casos en un "switch" en Go, es de arriba a abajo, la evaluacion se detendra cuando alguno de los casos se cumpla.

```golang

func main() {
	fmt.Print("Go corre en ");
	
    switch os := runtime.GOOS; os {
	    case "darwin":
		    fmt.Println("OS X.")
	    case "linux":	fmt.Println("Linux.")
	    
        default:
		    fmt.Printf("%s.\n", os) // windows, ...
	}
}
```

Cita: A Tout to Go, Switch. https://tour.golang.org/flowcontrol/9

Por ultimo, una de las formas en la que podemos utilizar un "switch" en Go, es sin condicional, los cual, le dara una semejancia a una cadena de "if-else", pero estructurado de forma mas limpia.

```golang

func main() {
	t := time.Now()
	switch {
	case t.Hour() < 12:
		fmt.Println("Buenos dias!")
	case t.Hour() < 17:
		fmt.Println("Buenas tardes.")
	default:
		fmt.Println("Buenas noches.")
	}
}

```

