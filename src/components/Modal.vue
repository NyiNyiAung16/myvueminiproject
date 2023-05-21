<template>
  <div class="backdrop">
    <div class="modal">
        <p>modal Content</p>
    </div>
  </div>
</template>

<script>
export default {

}
</script>

<style>
    .backdrop{
        background-color: black;
        width: 100%;
        height: 100%;
        position: fixed;
    }
    .modal{
        background-color: white;
        height: 200px;
        width: 200px;
    }
</style>