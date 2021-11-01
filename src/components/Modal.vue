<template>
  <div class="customModal" @click.self="closeModal">
    <p ref="modalText" :class="{ txtcolor: textcolor }">{{ modaltxt }}</p>
    <slot></slot>
    <div>
      <slot name="links"></slot>
    </div>
  </div>
  <!-- <button @click="changeModalText">Click Me!</button> -->
</template>

<script>
export default {
  data() {
    return {
      text: "Hello World",
    };
  },
  props: ["modaltxt", "textcolor"],
  methods: {
    changeModalText() {
      this.$refs.modalText.classList.add("clicked");
      this.text = "salam dottarrr!!!";
    },
    closeModal() {
      this.$emit("close");
    },
  },
};
</script>

<style scoped>
.customModal {
  background: gray;
  padding: 20px;
}
.txtcolor {
  color: yellow;
}
.clicked {
  background-color: yellow;
}
</style>