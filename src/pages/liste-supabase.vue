<script setup lang="ts">
import { supabase } from "../supabase";
import { ref } from "@vue/reactivity";
import Card from "../components/card.vue";
console.log("supabase :", supabase); // pour vérifier et "garder" supabase dans le code

const maison = [supabase];

const { data: tableauMaisons, error } = await supabase
    .from('Maison')
    .select('*')

console.log("Maison:", maison);

const user = ref(supabase.auth.user());

supabase.auth.onAuthStateChange(() => {
    user.value = supabase.auth.user()
})

</script>

<template>
    <div class="p-2">
        <h1 class="text-2xl">Page Liste</h1>
        <div v-for="Maison in tableauMaisons" :key="Maison.nom">
            <Card v-bind="Maison" />
        </div>
    </div>
</template>