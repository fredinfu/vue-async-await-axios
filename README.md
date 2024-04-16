# vue-async-await-axios

## Métodos async/await:
Simplifica la escritura y el manejo de código asíncrono sin tener que caer en callbacks anidados o un encadenamiento de promesas.

Ejemplo de codigo lleno de callbacks, conocido entre las comunidades de desarrollo como callback hell. 
```js
function loadConfig(callback) {
  // some async task
  callback(null, result);
}
function loadPokemonTrainer(result, callback) {
  // another async task
  callback(null, anotherResult);
}
function loadPokemonTeam(anotherResult, callback) {
  // final async task
  callback(null, finalResult);
}
loadConfig((error, result) => {
  if (error) {
    // handle error
  } else {
    loadPokemonTrainer(result, (error, anotherResult) => {
      if (error) {
        // handle error
      } else {
        loadPokemonTeam(anotherResult, (error, finalResult) => {
          if (error) {
            // handle error
          } else {
            // do something with final result
          }
        });
      }
    });
  }
});  
```
Ejemplo utilizando promesas con async await

```js
async function loadConfig() {
  // some async task
  return result;
}
async function loadPokemonTrainer(result) {
  // another async task
  return anotherResult;
}
async function loadPokemonTeam(anotherResult) {
  // final async task
  return finalResult;
}
async function main() {
  try {
    const result = await loadConfig(); // call the first function
    const anotherResult = await loadPokemonTrainer(result); // call the second function
    const finalResult = await loadPokemonTeam(anotherResult); // call the final function
    // do something with final result
  } catch (error) {
    // handle any error
  }
}
main();     
```

## Se usa ASYNC para declarar que una función retorna una promesa 
```js
async loadPokemonTeam(a){//load array of pokemon}
```

Se usa AWAIT para esperar a que una promesa se resuelva antes de proceder con la ejecución del código.
```js
async accessChampionLeague() {
  const result = await loadGymBadges(); // loads user Gym Badges when user is
}
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
