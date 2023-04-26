<script>
import links from "@/links.js";
import buttonEl from "@/components/buttonEl.vue";
export default {
  components: {
    buttonEl,
  },
  data() {
    return {
      isVisible: true,
      links: links.links,
    };
  },
};
</script>

<template>
  <div>
    <buttonEl
      :isVisible="isVisible"
      @update:isVisible="(val) => (isVisible = val)"
      buttonText="LINKS">
    </buttonEl>

    <div class="block">
      <div v-for="(item, index) in links" :key="index" v-show="isVisible">
        <a :href="item.link" 
          target="_blank"> 
            {{ item.name }} 
        </a>
      </div>
    </div>
  </div>
</template> 
