<template>
  <div id="app" class="container">
    <div class="row">
      <div class="col col-md-12">
        <pushwoosh></pushwoosh>
      </div>
    </div>
  </div>
</template>

<script>
import Pushwoosh from './components/Pushwoosh.vue'

export default {
  components: {
    Pushwoosh
  }
}
</script>

<style>
body {
  font-family: Helvetica, sans-serif;
}
</style>
