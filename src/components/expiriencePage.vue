<script>
import experience from "@/experience.js";
import buttonEl from "@/components/buttonEl.vue";
export default {
  components: {
    buttonEl,
  },
  data() {
    return {
      isVisible: false,
      experience: experience.experience,
    };
  },
};
</script>

<template>
  <div>
    <buttonEl
      :isVisible="isVisible"
      @update:isVisible="(val) => (isVisible = val)"
      buttonText="EXPIRIENCE">
    </buttonEl>
    <div class="block">
      <div v-for="(item, index) in experience" :key="index">
        <div v-show="isVisible"> 
          <a :href="item.link" target="_blank">
            <h5>
              {{ item.name }}
            </h5>
          </a>
          <p>{{ item.place }}</p>
          <p class="italic font-700">
            {{ item.time }}
          </p>
        </div>
      </div>
    </div>
  </div>
</template>
