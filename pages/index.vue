<script setup lang="ts">
import HeaderIntro from "@/components/HeaderIntro.vue";
import LatestBlogSection from "@/components/LatestBlogSection.vue";

useHead({ title: "Home" });
</script>

<template>
  <div>
    <HeaderIntro />

    <LatestBlogSection />
  </div>
</template>
