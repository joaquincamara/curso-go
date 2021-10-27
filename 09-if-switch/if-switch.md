## Sentencia if 

Ahoy! navegantes del ciberespacio, es esta seccion platicaremos sobre las diferentes formas de implementacion y uso que pueden tener las sentencias if en el lenguaje Go.

En Go el "if" funciona igual que muchos otros lenguajes, es un bloque, en el cual evaluaremos una expresion condicional, si la condicion se cumple(es verdadera), se ejecuta la seccion de codigo dentro de las llaves que corresponden al "if", si la condicion no se cumple no se ejecutara el codigo dentro de las llaves de nuestro "if", pero es posible ejecutar otras sentencias.

Una de las principales diferencias que podemos ver en los "if" en Go esta en su sintaxis, donde, la seccion de codigo que expresa la condicion no esta rodeada por parentesis como es normal en otros lenguajes de programcion.

En el siguiente ejemplo compararemos 2 numeros, con la condicion de que si son iguales imprimiremos en consola el mensaje "Los numeros son iguales", si los numeros no fuesen iguales, no se ejecutaria el codigo dentro de los parentesis del "if".

```golang

func main() {
    num1 := 1
    num2 := 1

    if num1 == num2 {
        fmt.Println("Los numeros son iguales")
    }
}
```

Como en la mayoria de los lenguajes de programacion, la sentecia "if", puede ir acompañada de un "else", permitiendo ejecutar el bloque de codigo dentro de los parentesis del "else" solo si la condicion del "if" no se cumple.

```golang

func main() {
    num1 := 1
    num2 := 2

    if num1 == num2 {
        fmt.Println("Los numeros son iguales")
    } else {
        fmt.Println("Los numeros son diferentes")
    }
}
```

Otras de las herramientas que podemos tener en los "if" de Go y que igual son comunes en la mayoria de los lenguajes de programacion, es la posibilidad de utilizar distintos operadores logicos para evaluar las condiciones.

De entre los mas comunes podemos ver:

```golang

func main() {
    num1 := 1
    num2 := 2
    num3 := 3

    // El operador "==" evalua si los valores son iguales
    if num1 == num2 {
        fmt.Println("Los numeros son iguales")
    }

    // El operador "!=" evalua si los valores no son iguales
    if num1 != num2 {
        fmt.Println("Los numeros son iguales")
    }

    // El operador "||" evalua si alguna de las 2 condiciones es verdadera, en el caso de que 1 lo sea, se ejecuta el codigo del "if"
    if num1 == num2 || num2 == num3{
        fmt.Println("Los numeros son iguales")
    }

    // El operador "||" evalua que ambas condiciones sean verdaderas, si lo son, se ejecuta el codigo del "if"
    if num1 == num2 && num2 == num3{
        fmt.Println("Los numeros son iguales")
    }
}
```

Algo interesante que podemos hacer con los "if" en Go, es que podemos hacer declaraciones de variables antes de la sentencia condicional, debemos considerar que los "if" en Go tienen un scope de bloque, esto quiere decir, decir que si declaramos una variable en la misma linea de la condicional, la variable solo sera accesibe dentro los parentesis del "if" o en todas sus anidaciones en caso de tenerlas.

```golang

func main() {
    if num := 9; num < 0 {
        fmt.Println(num, "es negativo")
    } else if num < 10 {
        fmt.Println(num, "tiene 1 digito")
    } else {
        fmt.Println(num, "tiene multiples digitos")
    }
}