## **Boleans**

Ahoy! mis hermano y hermanas del gremio de desarrolladores, el dia de hoy estudiaremos el tipo de dato "boolean" en el lenguaje de progrmacion Go, tambien veremos sus principales usos y aplicaciones.

Los booleans son uno de los tipos de dato mas simple con el que podemos trabajar en Go y en la mayoria de lenguajes de programcion, esto es, porque simplemente representan dos estados: verdadero o falso.

La forma de declarar una variable del tipo boolean en Go es miy sencilla:

```golang

func main() {
    var t bool = true
    var f bool = false
    fmt.Println(t) // true
    fmt.Println(f) // false
}
```

Con este tipo de variables, una de las cosas mas comunes que podemos hacer es usarlos como banderas. Por ejemplo, digamos que ests creando una aplicacion que envia un correo electronico a los usarios cada vez que uno de ellos acepta una nueva solicitud, entonces, para saber si esta accion se realizo podrias utilizar una variable del tipo boolean para informar que el usuario acepto una nueva solicitud.

Otro frecuente uso de las variables del tipo boolean es para saber el resultado de una operacion o prueba logica, un ejemplo de esto es crear una variable, en la cual, su valor sea el resultado de una prueba logica:

```golang

func main() {
    t := 2 == 2
    fmt.Println(t) // true

    f := 2 == 3
    fmt.Println(t) // false
```

En el ejemplo podemos ver que la variable t es igual al resultado de una prueba logica, en donde, probamos si el valor que se encuentra la izquiera de simbolo == es igual al que se encuentra a la derecha, entonces como es verdad o true que 2 es igual a 2, por lo tanto el valor de t sera true, en el caso de la variable f podemos ver que la prueba logica quiere comprobar si 2 es igual a 3, como ya sabemos el valor de f sera false porque 2 y 3 no son iguales.