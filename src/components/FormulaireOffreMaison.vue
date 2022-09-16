<script setup lang="ts">
import { ref } from "@vue/reactivity";
import Card from "./card.vue"
const maison = ref({})
</script>
<template>
    <div>
        <div class="p-2">
            <h2 class="text-2xl">Résultat (Prévisualisation)</h2>
            <Card v-bind="maison" />
        </div>
        <div class="p-2">
            <FormKit type="form" v-model="maison ">
                <FormKit name="nom" label="Lieu de la maison" />
                <FormKit name="price" label="Le prix de la maison" type="number" />
                <FormKit name="favoris" label="mettre en valeur" type="checkbox" />
            </FormKit>
        </div>
    </div>
</template>