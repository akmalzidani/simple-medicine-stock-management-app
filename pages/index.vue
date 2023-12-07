<template>
  <div><stokObat :drugs="drugs" :uri="uri"></stokObat></div>
</template>

<script setup>
import stokObat from "~/components/stokObat.vue";

const uri = `http://localhost:3005/api/products`;

const { data: response } = await useFetch(uri);

const drugs = response.value;
</script>

<style scoped>
/* Add component-specific styles here */
</style>
