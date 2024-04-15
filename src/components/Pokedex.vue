<template>
    <div>
        <input type="text" v-model="pokemon.name" placeholder="Pokemon..." class="textbox" >
        <p class="textbox">Pokemon Type: {{ pokemon.type }}</p>
        <button @click="asyncData" class="textbox">Fetch Pokemon</button>
        <img src="" alt="Pokemon Sprite" id="pokemonSprite" style="display: none;" class="textbox">
        <button @click="axios" class="textbox">Axios</button>
        <img src="" alt="Pokemon Sprite" id="pokemonSpriteBack" style="display: none;" class="textbox">
        <button @click="axiosAsync" class="textbox">Axios Async</button>
    </div>

</template>

<script>
    import axios from 'axios';

    export default {
        name: "Pokedex",
        data() {
            return {
                pokemon: {
                    name: "",
                    type: "",
                    img: ""
                },
                pokemonName: "",
                pokemonType: ""
            }
        },
        methods: {
            async asyncData() {
                try {
                    const url = "https://pokeapi.co/api/v2/pokemon/"+this.pokemon.name.toLowerCase();
                    console.log(url);
                    
                    


                    const response = await fetch(url)

                    if(!response){
                        throw new Error("Cannot fetch");
                    }

                    const data = await response.json();
                    

                    this.pokemon.type = data.types[0].type.name
                    

                    console.log(data);
                } catch (error) {
                    console.error(error);
                }
                
            },
            axios() {
                const img = document.getElementById("pokemonSprite");
                const url = "https://pokeapi.co/api/v2/pokemon/"+this.pokemon.name.toLowerCase();
                console.log(url);
                axios.get(url).then(response => {
                    
                    img.src = response.data.sprites.front_default;
                    img.style.display = "block"
                });
            },
            async axiosAsync() {
                try {
                    const img = document.getElementById("pokemonSpriteBack");
                    const url = "https://pokeapi.co/api/v2/pokemon/"+this.pokemon.name.toLowerCase();
                    const response = await axios.get(url);
                    img.src = response.data.sprites.back_default;
                    img.style.display = "block"
                } catch (error) {
                    console.error(error);
                }
            }
        }
    }
</script>
    
<style>
    .textbox{
        display: grid;
        grid-template-rows: auto;
        justify-items: center;
        align-items: center;
        margin: 0 auto 2rem;
    }
</style>