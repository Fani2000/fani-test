<template>
  <div>Message: {{ message }}</div>
</template>

<script setup>
import { onMounted, ref } from "vue";
import axios from 'axios'

const message = ref("");

onMounted(async () => {
 const res = await axios.get("api/getDetails") 
 console.log("RES: ", res.data)
 message.value = res.data

});
</script>
