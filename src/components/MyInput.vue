<script setup>
import { ref } from 'vue';


const person = ref({})

function safeFunction(){
    console.log(person.value)
}

</script>
<template>
    <form>
        <hr />
        <section>
            <p>Name</p>
            <input type="text" v-model="person.name">

        </section>
        <section v-if="person.name">
            <p>E-Mail</p>
            <input type="email" v-model="person.email">
            
        </section>
        <section v-if="person.email">
            <p>Passwort</p>
            <input type="password" v-model="person.password">
            
        </section>
        <section v-if="person.password">
            <p>Geburtstag</p>
            <input type="date" v-model="person.geburtstag">
        </section>
        <section v-if="person.geburtstag">
            <p>alter</p>
            <input type="number" v-model="person.alter">
        </section>
        <section v-if="person.alter<18">
            <p>Erziehungsbrechtigter</p>
            <input type="text" v-model="person.eltern">
        </section>
        <button @click.prevent="safeFunction">Speichern</button>

    </form>
    person{{ person }}
</template>