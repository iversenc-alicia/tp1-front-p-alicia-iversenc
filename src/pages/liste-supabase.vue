<template>
    <div class="p-2">
        <h1 class="text-2xl">Page Liste</h1>
        <div v-for="Maison in tableauMaisons" :key="Maison.nom">
            <Card v-bind="Maison" />
        </div>
    </div>
</template>

<script setup lang="ts">
import { supabase } from "../supabase";
import Card from "../components/card.vue";
console.log("supabase :", supabase); // pour vérifier et "garder" supabase dans le code

const maison = [supabase];

const { data: tableauMaisons, error } = await supabase
    .from('Maison')
    .select('*')

console.log("Maison:", maison);
</script>