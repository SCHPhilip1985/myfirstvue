<script setup>
import { ref } from 'vue';

const auto = ref({})

function safeFunction(){
    console.log(auto.value)
}

</script>
<template>
    <form>
        <section>
            <p>Automarke</p>
            <input type="text" v-model="auto.marke">
        </section>
        <section>
            <p>Verbrauch</p>
            <input type="number" v-model="auto.verbrauch">
        </section>
        <section>
            <p>Klasse</p>
            <select v-model="auto.klasse">
                <option value="Diesel">Diesel</option>
                <option value="Benzin">Benzin</option>
                <option value="Elektro">Elektro</option>

            </select>
        </section>
        <section>
            <p>Größe</p>
            <select v-model="auto.größe">
                <option value="Frauenpanzer">Frauenpanzer</option>
                <option value="Stadtmobil">Stadtmobil</option>
                <option value="Pampersbomber">Pampersbomber</option>

            </select>
        </section>

        <button @click.prevent="safeFunction">Speichern</button>
    </form>

auto {{ auto }}
</template>