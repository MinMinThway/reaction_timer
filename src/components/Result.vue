<template>
  <p>Result  is : {{ score }}mms </p>
  <div v-if="score < 400">
      <p>You are too fast</p>
  </div>
  <div v-else-if ="score > 400 && score < 600">
      <p>You are normal</p>
  </div>
  <div v-else>
      <p>You are to late</p>
  </div>
</template>

<script>
export default {
    props:['score']
}
</script>

<style>

</style>