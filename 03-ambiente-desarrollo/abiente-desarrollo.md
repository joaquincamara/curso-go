# Ambiente de desarrollo

Hola mundo!, en este video realizaremos los pasos para poder tener un ambiente de desarrollo desde cero, veremos como instalar Go en nuestra computadora, prepararemos la estructura basica de un proyecto y platicaremos acerca de los paquetes y modulos de Go.

### **Instalacion**

Instalar Go es muy sencillo, para este curso realizaremos los pasos para instalar Go en mac, pero no se preocupen dejare un link a la pagina oficial de Go donde podran encontrar los pasos para instalar el lenguaje segun su sistema operativo.

1. Con nuestro navegador vamos al sitio oficial de GO https://golang.org/
2. Hacemos click sobre el boton "download" para navegar a la seccion donde podremos descargar los los binarios de instalacion.
3. Seleccionamos el binario segun nuestro sistema operativo, en mi caso es Mac.
4. Una vez terminada la decarga, seleccionamos el binario para instalar Go.
5. Seguimos los pasos para la instalacion.
6. Una vez terminada la instalacion abrimos una terminal e ingresamos el comando:

```bash
$go version
```

7. Al ingresar el comando debemos de ver un output con la version de go que hemos instalado.

### **Hablemos sobre paquetes y modulos**

Antes de la version 1.11 todos los proyectos de Go se tenian que desarrollar dentro del GOPATH, este es una variable de entorno que define el directorio de trabajo, en mac por default el GOPATH esta definido en:

`/usr/local/go `

Obligandonos a tener todos nuestros proyectos dentro de esa URL. No era algo complicado de realizar pero requeria pasos extra que podian ser molestos para algunos de desarrolladores,las principales razones de esta practica eran:

- Las dependencias utilizadas por nuestro proyectos se instalan en el GOPATH, lo cual no nos permitia utilizarlas fuera del mismo.
- Antes de los modulos no existia con control de dependencias. (ocasionando problemas con el mero hecho del manejo de versiones, ocasionando problemas serios en el mantenimiento y desarrollo de proyectos).

Entonces que beneficios nos traen los Modulos en Go ?

1.
