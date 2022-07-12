

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

import { library } from '@fortawesome/fontawesome-svg-core'
import { faStar } from '@fortawesome/free-solid-svg-icons'

library.add(faStar)

export default {
  name: 'NHApp',
  components: {
    SpacePage
  }
}
</script>


<style>


#app {

}

</style>
