<template>
  <h1>Vue cli</h1>

  <div v-if="modalCondition">
    <Modal :theme="theme" @close="modalCondition=false">
      <h2>Login Success</h2>
      <p>Congrat</p>
      <p>We're looking forward to seeing you</p>
    </Modal>
  </div>

   <div v-if="deleteCondition">
    <modal :themetwo="themetwo" @close="deleteCondition=false">
      <h2>Are you sure want to delete?</h2>
      <p>yes or no?</p>
    </modal>
   </div>

  <button @click="modalCondition=true">open modal</button>
  <button @click="deleteCondition=true,change">delete modal</button>
</template>


<script>
import Modal from "./components/Modal.vue"
export default {
  components:{
    Modal
  },
  data(){
    return {
      theme:"success",
      themetwo:"delete",
      modalCondition:false,
      deleteCondition:false
    }
  },
}
</script>

<style scoped>
  h1{
    color: yellowgreen;
    font-style: italic;
  }
</style>