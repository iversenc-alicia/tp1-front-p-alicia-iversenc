<script setup lang="ts">
import {
    Disclosure,
    DisclosureButton,
    DisclosurePanel,
} from '@headlessui/vue';
import groupBy from "lodash/groupBy";
import { supabase } from "../../supabase";
const { data, error } = await supabase.from("quartiercommune").select("*");
if (error) console.log("n'a pas pu charger la table quartiercommune :", error);
</script>
    
<template>
    <section class="flex flex-col">
        <h3 class="text-2xl">Liste des quartiers</h3>
        <Disclosure v-for="(listeQuartier, libelleCommune) in groupBy(
          data,
          'libelle_Commune'
        )" :key="libelleCommune">
            <DisclosureButton> {{libelleCommune}}</DisclosureButton>
            <DisclosurePanel>
                <ul>
                    <li v-for="quartierObject in listeQuartier" :key="quartierObject.code_Quartier">

                        {{ quartierObject.libelle_Quartier }}
                    </li>
                </ul>
            </DisclosurePanel>
        </Disclosure>
    </section>
</template>