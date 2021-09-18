<template>
  <main>
    <h1>Modal</h1>
    <button @click="() => toggleModal('buttonTrigger')">Open</button>
    <Modal v-if="modalTrigger.buttonTrigger" 
    :toggleModal="() => toggleModal('buttonTrigger')">
      <h2>Text here</h2>
      </Modal>
  </main>
</template>

<script>
import {ref} from 'vue';
import Modal from './components/Modal.vue'

export default {
  setup() {
    const modalTrigger = ref({
      buttonTrigger: true,
    });

    const toggleModal = (trigger) => {
      modalTrigger.value[trigger] = !modalTrigger.value[trigger]
    }

    return {
      Modal,
      modalTrigger,
      toggleModal
    }
  },
    components: {
      Modal
  },
}
</script>

<style lang="scss" scoped>
main {
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  height: 100vh;
  padding: 50px;
  h1 {
    color: rgba($color: #686565b4, $alpha: 0.4);
    font-size: 10rem;
    text-shadow: 10px 0 0 black;
  }
  h2 {
    color: rgba($color: #686565b4, $alpha: 0.4);
    text-shadow: 4px 0 0 black;
    font-size: 4rem;
    letter-spacing: 4px;
    // font-weight: bolder;
    margin: 0px;
  }
    button {
    min-width: 150px;
    min-height: 50px;
    background: white;
    padding: 0.3rem 3.4rem;
    border: 3px solid black;
    margin-right: 2.6rem;
    box-shadow: 0 0 0 black;
    transition: all 0.2s;
    cursor: pointer;
    &:hover {
      box-shadow: 0.4rem 0.4rem 0 black;
      transform: translate(-0.4rem, -0.4rem);
    }
    &:active {
        box-shadow: 0 0 0 black;
        transform: translate(0, 0);
    }
  }
}

</style>
