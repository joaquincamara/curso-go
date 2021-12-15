## Goroutines

Ahoy de nuevo nagavegantes del interntet, en este capitulo aprenderemos sobre uno de los mecanismos mas interesantes en Go, las cuales son, las goroutines, utilizadas para el desarrollo de software concurrente.

En terminos sencillos las "goroutines", son hilos o threads muy ligeros que son manejados por el tiempo de ejemcucion de Go. En conjunto con los channels, podemos realizar programacion concurrente. En Go, cuando un programa inicia, por default corre una "goroutine", la cual es, la funcion main(), que encontramos en todos los programas escritos en Go.

Para crear una nueva goroutine, es necesario utilizar la palabra reservada "go", antes de la ejecucion de una funcion:

```golang


```