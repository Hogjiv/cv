<script>
import skills from "@/skills.js";
import buttonEl from "@/components/buttonEl.vue";
export default {
  components: {
    buttonEl,
  },
  data() {
    return {
      isVisible: true,
      skills: skills.skills,
    };
  },
};
</script>

<template>
  <div>
    <buttonEl
      :isVisible="isVisible"
      @update:isVisible="(val) => (isVisible = val)"
      buttonText="SKILLS"
    >
    </buttonEl>

    <div class="block">
      <span v-for="(item, index) in skills" :key="index" v-show="isVisible">
        <h5>Web development skills:</h5>
        <p>{{ item.webDev.join(", ") }}</p>
        <h5>3d skills:</h5>
        <p>{{ item.threeD.join(", ") }}</p>
        <h5>Web design skills:</h5>
        <p>{{ item.webDesign.join(", ") }}</p>
      </span>
    </div>
  </div>
</template>
