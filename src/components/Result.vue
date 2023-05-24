<template>
  <div v-if="scoreResult<200">
    <img src="https://shorturl.at/bjr57" alt="fast">
     <p>Result is {{scoreResult}}ms</p>
    <p>OMG You are so fast!</p>
  </div>

  <div v-else-if="scoreResult>200 && scoreResult<500">
    <img src="https://shorturl.at/nsINR" alt="normal">
     <p>Result is {{scoreResult}}ms</p>
    <p>You are just a normal</p>
  </div>

  <div v-else>
    <img src="https://shorturl.at/hwB48" alt="try again">
     <p>Result is {{scoreResult}}ms</p>
    <p>You are really slow.Try again!</p>
  </div>

</template>

<script>
export default {
    name:"ResultView",
    props:['scoreResult']
}
</script>

<style>

</style>