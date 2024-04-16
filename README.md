# vue-async-await-axios

## Métodos async/await:
Simplifica la escritura y el manejo de código asíncrono sin tener que caer en callbacks anidados o un encadenamiento de promesas.

![image](https://github.com/fredinfu/vue-async-await-axios/assets/23424560/ee46c789-22db-4865-b0d7-03aaedb4d1a4)


## Se usa para declarar que una función retorna una promesa 
```sh
async
```

Se usa para esperar a que una promesa se resuelva antes de proceder con la ejecución del código.
```sh
await
```

## Axios
Axios es una librería JavaScript que se utiliza para realizar peticiones HTTP desde el navegador o desde Node.js.

## Ejemplo Axios 

![image](https://github.com/fredinfu/vue-async-await-axios/assets/23424560/2cafb6ce-2b05-461f-940c-1bc1de5a0801)

## Ejemplo Axios Asyncrono

![image](https://github.com/fredinfu/vue-async-await-axios/assets/23424560/5838e6ce-e795-4dc0-9f93-c18d4ed28590)


## Instalar dependencias al proyecto
Es necesario instalar axios en el proyecto si lo queremos importar. 

```sh
npm install axios
```

```sh
.
.
.
import axios from 'axios';
const response = await axios.get(url);
```

## Project Setup

```sh
npm install
```

### Compile and Hot-Reload for Development

```sh
npm run dev
```

### Compile and Minify for Production

```sh
npm run build
```
