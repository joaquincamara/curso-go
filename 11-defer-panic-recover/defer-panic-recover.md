## Defer, Panic y Recover

### **Defer**

Ahoy! de nuevo navegantes de la web, en esta seccion aprenderemos tres de los conceptos mas importantes que tenemos en Go, los cuales son, las funciones Panic, Recover y Defer, las cuales, son utilizadas de forma muy extendida en los sistemas creados con Go para hacer los programas mas eficientes y acceder a diferentes estilos de programacion, como la programacion concurrente.

Comenzaremos con la palabra reservada "defer", su funcion nos permite retrasar la ejecucion de una funcion que tenga junto a ella la palabra "defer" hasta que la funcion que encierra a la funcion diferida termine termine su ejecucion, algo importante que tenemos que recordar, es que los argumentos de la funcion diferida son evaluados inmediatamente pero la funcion no se ejecuta hasta que la funcion que la rodea termine.  

```golang

func main() {
    defer fmt.Println("world") // diferida hasta que main() termine
    fmt.Println("hello")
 }

    // imprime:
    // hello
    // world
```

Una de las situaciones mas comunes en las que se utiliza "defer", es cuando tenemos que lidear con el cierre de conexiones, entre ellas la mas comun es cuando tenemos que cerrar un "response" de HTTP, ahora, podran pensar, porque no simplemente cerramos la conexion justo despues de lidear con el "response" ?, bueno, la principal razon es porque normalmente las funciones que interactuan de alguna forma por medio de HTTP, pueden llegar a tener varios puntos de retorno y si no usamos un "defer", tendriamos que cerrar nuestra conexion en cada uno de los posibles returns, pero si utilizamos un "defer" para cerrar la conexion nos aseguramos de que nuestra conexion se cierre sin importar el punto de retorno que se haya ejecutado en nuestra funcion.

```golang

func (h *aboutMeHandler) Post(w http.ResponseWriter, r *http.Request) {
	p := &aboutMe.AboutMe{}
	err := json.NewDecoder(r.Body).Decode(&p)

	if err != nil {
		http.Error(w, http.StatusText(http.StatusInternalServerError), http.StatusInternalServerError)
		return
	}
	defer r.Body.Close()

	err = h.aboutMeService.Add(p)

	if err != nil {
		http.Error(w, http.StatusText(http.StatusInternalServerError), http.StatusInternalServerError)
		return
	}
	json.NewEncoder(w).Encode(&p)
}
```

Como pueden ver en el ejemplo anterior, la funcion "Post" tiene varios puntos de retorno o "return", en donde tendriamos que cerrar nuestra conexion por medio de "r.Body.Close()", pero gracias a que utilizamos la palabra "defer", para retrazar la ejecucion de "r.Body.Close()", hasta que "Post" ejecute algun "return" podemos estar seguros de que "r.Body.Close()" se ejecutara.


### **Panic**

Ahora, hablaremos sobre la funcion integrada "Panic". Como ya sabemos, Go es un lenguaje compilado, esto quiere decir que la mayoria de los errores son detectados durante el tiempo de compilacion, pero algunos errores como intentar acceder a algun elemento  que se encuentra fuera del limite de un array tienen que ser checados en tiempo de ejecucion. Cuando Go detecta algun error similar a este, el programa realiza un "panic", el cual se encarga detener la ejecucion de programa. 

si quisieramos simular este mecanismo, tendriamos que usar la funcion "panic()", la cual, termina el tiempo de ejecucion y nos da un mensaje de error.

```golang

func main() {
    var name string = "Joaquin"

    if name == nil {
        panic("name need to be a string")
    }

}
```

### **Recover**

Go nos brinda una forma de recuperarnos de un "panic", el cual es por medio de la funcion integrada "recover", la cual es llamada dentro una funcion diferida, el "recover", se encargara de detener el estado de "panic", en el sistema y regresara un mensaje de error construido en el mensaje de error implementado en la funcion "panic" sin terminar la ejecucion del programa.

```golang

func main() {
    fmt.Println(printName("Joaquin")) // imprime: Joaquim
    fmt.Println(printName(nil)) // imprime: recovered from name need to be a string
}

func printName(name string) string {
    defer IwillExecuteRecover()
    if name == nil {
        panic("name need to be a string")
    }

    return fmt.Sprintf("%s \n", *name)
}

func IwillExecuteRecover() {
    if r := recover(); r != nil {
        fmt.Println("recovered from", r)
    }
}
```

En el ejemplo anterior podemos ver que se implementa la funcion diferida  "IwillExecuteRecover()", la cual, contiene un recover que se activa en el momento de que un "panic()" es ejecutado.

Para el lector mas veterano, podria decir que estas dos funciones se tratan de un try - catch, como los que podemos encontrar en lenguajes como Javascript y anque es posible simular el comportamiento de dichos elementos por medio de "panic" y "recover", es altamente recomendado no utilizar estas funciones como un try - catch, si no mas bien regresar un "error" cuando esto sea necesario. 

