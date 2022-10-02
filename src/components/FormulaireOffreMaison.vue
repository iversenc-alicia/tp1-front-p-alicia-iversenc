<script setup lang="ts">
import { ref } from "@vue/reactivity";
import Card from "./card.vue";
import { supabase } from '@/supabase';
import { useRouter } from "vue-router";

const router = useRouter();
const maison = ref({});

const props = defineProps(["id"]);
if (props.id) {
    // On charge les données de la maison
    let { data, error } = await supabase
        .from("Maison")
        .select("*")
        .eq("id", props.id);
    if (error) console.log("n'a pas pu charger le table Maison :", error);
    else maison.value = (data as any[])[0];
}



//, favoris: true
async function upsertMaison(dataForm, node) {
    const { data, error } = await supabase.from("Maison").upsert(dataForm);
    if (error || !data) node.setErrors([error?.message])
    else {
        node.setErrors([]);
        router.push({ name: "edit-id", params: { id: data[0].id } });
    }
}



</script>
<template>
    <div class="flex flex-row-reverse justify-center">
        <div class="p-2">
            <h2 class="text-2xl">Résultat (Prévisualisation)</h2>
            <Card class="w-3/4 m-auto" v-bind="maison" />
        </div>
        <div class="p-5">
            <FormKit @submit="upsertMaison" type="form" v-model="maison " :config="{
            classes: {
            input: 'p-1 rounded border-gray-400 shadow-m border',
            label: 'text-gray-800',
            },
            }" :submit-attrs="{ classes: { input: 'bg-red-500 p-2 rounded' } }">
                <FormKit name="nom" label="Lieu de la maison" />
                <FormKit name="price" label="Le prix de la maison" type="number" />
                <FormKit name="Quartier" label="L'adresse de la maison'" />
                <FormKit name="nbbath" label="Nombre de salle de bain" />
                <FormKit name="nbsize" label="Surface" />
                <FormKit name="nbbed" label="Nombre de chambres" />
                <!-- <FormKit name="favoris" label="mettre en valeur" type="checkbox" wrapper-class="flex" /> -->
            </FormKit>
        </div>
    </div>
</template>