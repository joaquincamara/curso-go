# **Runes**

Ahoy mis amigas y amigos del gremio de desarrolladores, en esta ocasion estudiaremos las runes en Go y algunas de las principales aplicaciones que podemos darle a este tipo de dato.

En el pasado, solo utilizabamos con un conjunto de caracteres que se conoce como ASCII o el Código Estándar Americano para el Intercambio de Información. Se usaban 7 bits para representar 128 caracteres, incluidas letras en inglés mayúsculas y minúsculas, dígitos y una variedad de signos de puntuación y caracteres de control de dispositivos. Debido a esto, una gran parte de la población del mundo no puede usar su propio sistema de escritura en la computadora. Entonces, para resolver este problema, se invento Unicode. Es un superconjunto de ASCII y contiene todos los caracteres presentes en el sistema de escritura del mundo, incluidos acentos y otras marcas diacríticas, códigos de control como tabulación, y asigna a cada uno un número estándar llamado punto de código Unicode, o en el idioma Go, una runa. El tipo de runa es un alias de int32.

Puntos importantes:

Siempre hay que considerar que una cadena es una secuencia de bytes, no de una runa. Pero es posible que una cadena contenga texto Unicode codificado en UTF-8 y, como sabíamos que el código fuente de go siempre se codifica como UTF-8, no es necesario codificar la cadena en UTF-8.
UTF-8 codifica todos los Unicode entre 1 y 4 bytes, donde 1 byte se usa para ASCII y el resto se usa para la runa.

ASCII contiene un total de 256 elementos. En el que 128 son caracteres y 0-127 se identifican como puntos de código. Aquí el punto de código se refiere al elemento que representa un valor único.

```golang

func main() {
    var r rune = 'a'
    fmt.Println(a) // 97
}
```