<template>
  <div class="backdrop" @click.self="closeModal">
    <div class="modal" :class="{success:theme==='success',delete:themetwo==='delete'}">
      <slot>I don't receive any html template</slot>
    </div>
  </div>
</template>

<script>
export default {
  name:"ModalView",
  props:['theme','themetwo'],
  methods:{
    closeModal(){
      this.$emit("close")
    }
  }
}
</script>

<style scoped>
    .backdrop{
        top:0;
        background-color: gray;
        width: 100%;
        height: 100%;
        position: fixed;
    }
    .modal{
        background-color: white;
        width: 400px;
        padding: 20px;
        border-radius: 20px;
        margin: 100px auto;
    }
    .success{
      background-color: green;
      color: white;
    }
    .delete{
      background-color: red;
      color: white;
    }
</style>