<template>
  <div>
    <detailObat :obat="drug" :uriUpdateStock="uriUpdateStock"></detailObat>
  </div>
</template>

<script setup>
import detailObat from "~/components/detailObat.vue";

const { id } = useRoute().params;
const uriUpdateStock = `http://localhost:3005/api/products`;
const uri = `http://localhost:3005/api/products/${id}`;

const { data: response } = await useFetch(uri);

const drug = response.value;
</script>

<style scoped></style>
