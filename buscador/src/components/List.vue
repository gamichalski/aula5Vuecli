<template>
<div class="has-text-centered">
  <span class="is-size-5 has-text-weight-bold">{{title}}</span>
  <ul>
    <li v-for="(item, index) in items" :key="index">{{item}}</li>
  </ul>
</div>
</template>

<script>
export default {
  props: {
    title: String,
    items: Array
  }
}
</script>

<style lang="scss">

</style>