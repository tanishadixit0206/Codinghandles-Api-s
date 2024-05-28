<script setup lang="ts">
import { onMounted } from "vue";
import SwaggerUI from "swagger-ui-dist/swagger-ui.es-bundle.js";
import "swagger-ui-dist/swagger-ui.css";

onMounted(() => {
  SwaggerUI({
    dom_id: "#swagger-ui",
    url: "",
  });
});
</script>

<template>
  <div id="swagger-ui"></div>
</template>

<style scoped></style>
