## Defer, Panic y Recover

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

