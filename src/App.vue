<template>
  <div class="app container">
    <h1>TODO</h1>
    <ToDo/>
  </div>
</template>

<script>

import ToDo from "@/components/ToDo";
export default {
  name: 'App',
  components: {
    ToDo
  }
}
</script>

<style>

</style>
