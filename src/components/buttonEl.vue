<script>
export default {
  data() {
    return {
      isActive: true,
      isArrowRotate: false,
    };
  },
  props: {
    isVisible: {
      type: Boolean,
      required: true,
    },
    buttonText: {
      type: String,
      required: true,
    },
  },
  methods: {
    visibility() {
      this.$emit("update:isVisible", !this.isVisible);
    },
    meth() {
      console.log("sdfdsf");
    },
    rotateArrow() {
      this.isArrowRotate = !this.isArrowRotate;
    },
  },
};
</script>
<template>
  <div class="d-flex align-items-center">
    <svg
      class="arrow-move"
      :class="{ isArrowRotate: isArrowRotate, arrow: isArrowRotate }"
      xmlns="http://www.w3.org/2000/svg"
      viewBox="0 0 448 512"
      width="20"
      height="20"
      transform="rotate(-90)"
    >
      <path
        d="M9.4 233.4c-12.5 12.5-12.5 32.8 0 45.3l160 160c12.5 12.5 32.8 12.5 45.3 0s12.5-32.8 0-45.3L109.2 288 416 288c17.7 0 32-14.3 32-32s-14.3-32-32-32l-306.7 0L214.6 118.6c12.5-12.5 12.5-32.8 0-45.3s-32.8-12.5-45.3 0l-160 160z"
        fill="#7ca7a5"
      />
    </svg>
    <div @click="rotateArrow()">
      <button type="submit" 
        @click="visibility" 
        class="title">
          {{ buttonText }}
      </button>
    </div>
  </div>
</template>

<style>
.arrow {
  transform: rotate(90deg);
  fill: #7ca7a5;
}
.title {
  color: #7ca7a5;
  font-size: 25px;
  font-weight: 700;
  background-color: transparent;
  border-color: transparent;
  outline: none;
  padding: 0;
  border: o;
}
.title:hover {
  border-color: transparent;
  outline: none;
}

.title:focus {
  background-color: transparent;
  border-color: transparent;
  outline: none;
}
</style>
