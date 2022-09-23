<script setup lang="ts">
import FormulaireOffreMaison from "../../components/FormulaireOffreMaison.vue";
defineProps({
    id: String,
})

</script>

<template>
    <div>
        <FormulaireOffreMaison :id="id" />
    </div>
</template>
