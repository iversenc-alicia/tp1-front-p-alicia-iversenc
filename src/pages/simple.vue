<template>
    <div class="p-4">
        <h1 class="text-2xl">Page Simple</h1>
        <card class="w-1/2" v-bind="objet" />
    </div>
</template>
    
<script setup lang="ts">
import card from "../components/card.vue";

const objet = { nom: "Maison sur la coline", price: 750, favoris: true, txt: "Ecosse", nbbath: 3, nbsize: "450 m²", img: "/public/maison.jpg" }
</script>