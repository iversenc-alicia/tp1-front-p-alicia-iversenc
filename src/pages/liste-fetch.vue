<template>
    <div class="p-2">
        <h1 class="text-2xl">Page Liste</h1>
        <div v-for="maison in tableauMaisons" :key="maison.nom">
            <card class="w-1/2" v-bind="maison" />
        </div>
    </div>
</template>

<script setup lang="ts">
import card from "../components/card.vue";

const res = await fetch("tableauMaisons.json");
const tableauMaisons = await res.json();

</script>