<template>
  <div>
    <button
      class="
        bg-blue-600
        text-white
        px-4
        py-2
        text-sm
        uppercase
        tracking-wide
        font-bold
        rounded-lg
      "
      @click="exampleModalShowing = true"
    >
      Show Modal
    </button>
    <CardModal
      :showing="exampleModalShowing"
      @close="exampleModalShowing = false"
    >
      <h2 class="text-xl font-bold text-gray-900">Example modal</h2>
      <p class="mb-6">
        This is example text passed through to the modal via a slot.
      </p>
      <button
        class="
          bg-blue-600
          text-white
          px-4
          py-2
          text-sm
          uppercase
          tracking-wide
          font-bold
          rounded-lg
        "
        @click="exampleModalShowing = false"
      >
        Close Modal
      </button>
    </CardModal>
  </div>
</template>
<script>
import CardModal from './CardModal.vue';
export default {
  components: {
    CardModal,
  },
  data() {
    return {
      exampleModalShowing: false,
    };
  },
};
</script>
