<script setup>
import { ref } from 'vue';

const moviesFromLS = JSON.parse(localStorage.getItem("movies"))
console.log("moviesFromLS : ",moviesFromLS)
const movies=ref(moviesFromLS||[])
const movie = ref({})

function storeMovie(){
    movies.value.push(JSON.parse(JSON.stringify(movie.value)))
    localStorage.setItem("movies", JSON.stringify(movies.value))
}
</script>

<template>
    <form>
        <input type="text" v-model="movie.title" placeholder="Titel">
        <input type="number" v-model="movie.number" placeholder="Erscheinungsjahr">
        <select v-model="movie.kategorie" >
            <option value="Krimi">Krimi</option>
            <option value="Drama">Drama</option>
            <option value="Satire">Satire</option>

        </select>
        <button @click.prevent="storeMovie()">Zur Collection hinzufügen</button>
    </form>
    <article>
        <div>
            <section>
                Titel
            </section>
            <section>
                Erscheinungsjahr
            </section>
            <section>
                Kategorie
            </section>
        </div>
        <div v-for="film in movies">
            <section>
                {{ film.title }}
            </section>
            <section>
                {{ film.number }}
            </section>
            <section>
                {{ film.kategorie }}
            </section>
        </div>
    </article>

</template>
<style scoped>
    div{
        display: flex;
        justify-content: space-around;
        
    }
    div:first-child{
        background-color: grey;
        color: white;
    }
    
</style>