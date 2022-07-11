

<template>


    <div id="app">
      <div class="app__header">
        natural history museum
      </div>
      <space-page></space-page>
    </div>


</template>

<script>
import SpacePage from "./SpacePage.vue";

export default {
  name: 'NHApp',
  components: {
    SpacePage
  }
}
</script>


<style>


#app {
  max-width: 1280px;
  margin: 0 auto;
  padding: 2rem;

  font-weight: normal;
}

</style>
