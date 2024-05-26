<script lang="ts">
import { defineComponent } from "vue";
import LogoItem from "../components/LogoItem.vue";
import AccessTokenContainer from "../components/AccessTokenContainer.vue";
export default defineComponent({
  name: "LandingPage",
  components: { LogoItem, AccessTokenContainer },
});
</script>

<template>
  <div>
    <LogoItem />
    <div>
      <AccessTokenContainer />
    </div>
  </div>
</template>
