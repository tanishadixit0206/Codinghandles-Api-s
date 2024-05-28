<script setup lang="ts">
import { ref } from "vue";
import axios from "axios";
const accessToken = ref<string | null>(null);

const signInWithGoogle = () => {
  const clientId = import.meta.env.VITE_CLIENT_ID;
  const redirectUri = import.meta.env.VITE_REDIERECT_URL;
  const googleAuthUrl = `https://accounts.google.com/o/oauth2/v2/auth?client_id=${clientId}&redirect_uri=${redirectUri}&response_type=code&scope=email profile openid`;
  window.location.href = googleAuthUrl;
};

const getAccessToken = async (code: string) => {
  const clientId = import.meta.env.VITE_CLIENT_ID;
  const clientSecret = import.meta.env.VITE_CLIENT_SECRET;
  const redirectUri = import.meta.env.VITE_REDIERECT_URL;

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

</script>

<template>
  <div>
    <h1>Sign In</h1>
    <div @click="signInWithGoogle">
      <img src="" />
      Sign in with Google
    </div>
  </div>
</template>

<style scoped></style>
