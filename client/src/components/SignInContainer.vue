<script lang="ts">
import { ref } from "vue";
import axios from "axios";

const accessToken = ref<string | null>(null);

const signInWithGoogle = () => {
  const clientId = "";
  const redirectUri = "";
  const googleAuthUrl = "";
  window.location.href = googleAuthUrl;
};

const getAccessToken = async (code: string) => {
  const clientId = "";
  const clientSecret = "";
  const redirectUri = "";

  try {
    const response = await axios.post("", {
      code,
      client_id: clientId,
      client_secret: clientSecret,
      redirect_uri: redirectUri,
      grant_type: "authorization_code",
    });
    accessToken.value = response.data.access_token;
  } catch (error) {
    console.error("Failed to exchange code for access token", error);
  }
};

const urlParams = new URLSearchParams(window.location.search);
const code = urlParams.get("code");

if (code) {
  getAccessToken(code);
}

export default {
  name: "SignInContainer",
};
</script>

<template>
  <div>
    <h1>Sign In</h1>
    <button href="">
      <img src="" />
      Sign in with Google
    </button>
  </div>
</template>

<style scoped></style>
