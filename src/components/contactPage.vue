<script>
import contacts from "@/contacts.js";
export default {
  data() {
    return {
      contacts: contacts.contacts,
      isVisible: false,
    };
  },
};
</script>

<template>
  <div>
    <div class="block">
      <div
        v-for="(item, index) in contacts"
        :key="index"
        class="d-flex flex-column"
      >
        <h5>
          {{ item.name }}
        </h5>
        <a :href="item.link" target="_blank">
          {{ item.value }}
        </a>
      </div>
    </div>
  </div>
</template>

<style scoped>
.block a {
  color: rgb(215, 215, 215) !important;
}
.block p {
  margin-bottom: 0;
}
</style>
