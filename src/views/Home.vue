<template>
  <div class="home">
    <Modal @close="toggleModal" :modalActive="modalActive">
      <div class="modal-content">
        <h1>This is a Modal Header</h1>
        <p>This is a modal message</p>
      </div>
    </Modal>
    <button type="button" role="button" @click="toggleModal">Open Modal</button>
  </div>
</template>

<script>
// @ is an alias to /src
import Modal from "@/components/Modal.vue";
import { ref } from "vue";

export default {
  name: "Home",
  components: {
    Modal,
  },

  setup() {
    const modalActive = ref(true);
    const toggleModal = () => {
      modalActive.value = !modalActive.value;
    };

    return { modalActive, toggleModal };
  },
};
</script>


<style lang="scss">
.home {
  background-color: rgba(0, 176, 234, 0.5);
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;

  .modal-content {
    display: flex;
    flex-direction: column;

    h1,
    p {
      margin-bottom: 16px;
    }

    h1 {
      font-size: 32px;
    }
    p {
      font-size: 18px;
    }
  }
}
</style>