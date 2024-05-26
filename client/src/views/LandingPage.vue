<script lang="ts">
import { defineComponent } from "vue";
import LogoItem from "../components/LogoItem.vue";
import SignInContainer from "../components/SignInContainer.vue";
export default defineComponent({
  name: "LandingPage",
  components: { LogoItem, SignInContainer },
});
</script>

<template>
  <div>
    <LogoItem />
    <div>
      <SignInContainer />
    </div>
  </div>
</template>
