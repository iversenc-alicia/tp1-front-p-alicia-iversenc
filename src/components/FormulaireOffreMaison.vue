<script setup lang="ts">
import { ref } from "@vue/reactivity";
import Card from "./card.vue"
const maison = ref({ nom: "Adresse", price: 500, favoris: true, txt: "Lieu", nbbath: 5, nbsize: "200m2", img: "/maison.jpg" });
</script>
<template>
    <div>
        <div class="p-2">
            <h2 class="text-2xl">Résultat (Prévisualisation)</h2>
            <Card class="w-3/4 m-auto" v-bind="maison" />
        </div>
        <div class="p-5">
            <FormKit type="form" v-model="maison " :config="{
            classes: {
            input: 'p-1 rounded border-gray-400 shadow-m border',
            label: 'text-gray-800',
            },
            }" :submit-attrs="{ classes: { input: 'bg-red-500 p-2 rounded' } }">
                <FormKit name="nom" label="Lieu de la maison" />
                <FormKit name="price" label="Le prix de la maison" type="number" />
                <FormKit name="favoris" label="mettre en valeur" type="checkbox" wrapper-class="flex" />
            </FormKit>
        </div>
    </div>
</template>