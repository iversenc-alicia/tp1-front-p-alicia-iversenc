<template>
    <div class="p-2">
        <h1 class="text-2xl">Page Liste</h1>
        <div v-for="maisons in maisons" :key="maisons.nom">
            <card class="w-1/2" v-bind="maisons" />
        </div>
    </div>
</template>

<script setup lang="ts">
import card from "../components/card.vue";

const maisons = [{ nom: "test", price: 750, favoris: true, txt: "Ecosse", nbbath: 5, nbsize: "48 m²", img: "/public/maison.jpg" }, { nom: "test2", price: 590, favoris: false, txt: "Angleterre", nbbath: 2, nbsize: "84 m²", img: "/public/maison2.jpg" }, { nom: "Canada", price: 850, txt: "Dernier produit de test", nbbath: 1, nbsize: "52 m²", img: "/public/maison3.jpg" }]
//   import maisons from "../assets/maisons.json";
</script>