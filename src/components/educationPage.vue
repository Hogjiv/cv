<script>
import education from "@/education.js";
import buttonEl from "@/components/buttonEl.vue";
export default {
  components: {
    buttonEl,
  },
  data() {
    return {
      isVisible: false,
      education: education.education,
    };
  },
};
</script>

<template>
  <div>
    <buttonEl
      :isVisible="isVisible"
      @update:isVisible="(val) => (isVisible = val)"
      buttonText="EDUCATION"
    >
    </buttonEl>

    <div class="block">
      <div v-for="(item, index) in education" :key="index" v-show="isVisible">
        <h5>{{ item.name }}</h5>
        <p>{{ item.time }}</p>
      </div>
    </div>
  </div>
</template>
