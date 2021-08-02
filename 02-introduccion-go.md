# Introducción al lenguaje de programción GO

Hola mundo! en este video platicaremos un poco sobre el lenguaje de Go para poder conocer sobre su transfondo, permitiendonos entender mejor sus conceptos y poder llevarlos a la practica de manera sencilla.

### Comencemos con un poco de historia:

Go fue creado por Rob Pike, Robert Griesemer y Ken Thompson en google, los 3 han realizadó aportaciones al mundo de desarrollo de software que lo han moldeado a como lo conocemos hoy en día.

En google se llegó a la conclusión que algunos de los lenguajes usados para diferentes desarrollos tenian detalles, que en cierto punto dificultaban o podrian llegar a dificultar el proceso de desarrollo.

### Aqui fue donde Go llegó a traer los siguientes featuers:

- Go es un lenguaje compilado

  - Con esto nos referimos a que antes de ser ejecutado, el codigo es procesado por un "compilador", el cual genera un archivo en codigo binario, tambien conocido como lenguaje maquina, para ser ejecutado por la computadora.

- Es un lenguaje fuertemente tipado.

  - Esto quiere decir que la comprovacion de los tipos de datos que utilicemos en nuestras variables serán comprobadas durante el tiempo de compilación y no durante la ejecución del programa.

- Su comunidad se a vuelto extensa y muy activa.

  - Esto es muy importante, ya que la comunidad que rodea a Go genera librerias, participa en el desarrollo del lenguaje, volviendolo mas popular y rico en diferentes herramientas que los desarrolladores pueden utilizar para crear programas eficientes.

- Su sintaxis es simple.

  - Aunque es verdad que algunos conceptos de Go llevan a una curva de aprendizaje, su sintaxis simple ayuda a entender rapidamente a los nuevos desarrolladores como utilizar el lenguaje y facilita el mantenimiento en proyectos ya existentes.

- Fue creado con y para concurrencia.

  Concurrencia es un concepto el cual aplicado permite a los programas ejectutar varias funciones, mas adelante hablaremos a detalle sobre este tema, las principales ventajas de haber creado Go bajo este esquema son:

  - El timepo de compilacion es corto en comparacion a otros lenguajes compilados.
  - El garbage collector es eficiente y en muchos casos no se percibe.
  - Utilizar concurrencia en Go es sencillo y eficiente.

- Genera binarios funcionales para multiples sistemas operativos.

  Al terminar el proceso de compilacion y construccion de nuestro programa Go generara un binario ejecutable para diversos sistemas operativos como Mac, windows, Ubuntu, etc. Lo que vuelve la distribucion del sistema bastente sencilla.
