<template>
    <div style="background: white; min-height: 100vh">
      <v-container class="text-center">
        <v-row>
          <v-col class="mt-12">
            <h1 style="font-size: 120px; color: black">404</h1>
            <p>Page not found</p>
            <v-btn class="mt-8" @click="goHome">Go Home</v-btn>
          </v-col></v-row
        ></v-container
      >
    </div>
  </template>
  
  <script setup>
  const query = useRoute().query;
  const router = useRouter();
  const referrer = ref(
    query.referrer ? decodeURIComponent(query.referrer) : null
  );
  const goHome = () => router.push("/");
  useHead({
  title: "404 Page Not Found",
  meta: [
    {
      name: "description",
      content: "404 - Page not found",
    },
  ],
});
  </script>