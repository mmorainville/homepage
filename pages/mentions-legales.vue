<template>
  <div class="mentions-legales">
    <header class="w-full flex px-2 py-2 container mx-auto">
      <nuxt-link to="/"
        ><p class="text-sm font-bolder">&larr; retour</p></nuxt-link
      >
    </header>

    <div class="container lg:px-24 px-12 mt-24 lg:mt-12 mb-12 mx-auto">
      <nuxt-content class="prose" :document="data" />
    </div>

    <app-footer />
  </div>
</template>

<script>
export default {
  async asyncData({ $content }) {
    const data = await $content('mentions-legales').fetch();
    return {
      data,
    };
  },
};
</script>

<style lang="scss">
.mentions-legales {
  ul {
    @apply list-disc;
    @apply list-inside;
    @apply mb-6;
  }
}
</style>

