<template>
  <header
    class="
      bg-gradient-to-r
      from-purple-400
      via-pink-500
      to-red-500
      grid
      justify-items-center
    "
  >
    <h1>My Contacts</h1>
    <input
      class="shadow border rounded p-2 leading-tight"
      v-model="searchQuery"
      @input="onSearchChange"
      type="text"
      name="search"
      id="search"
      placeholder="Search contacts"
    />
  </header>
</template>

<script>
import { ref } from "vue";
export default {
  setup(props, { emit }) {
    const searchQuery = ref("");
    function onSearchChange() {
      emit("search", searchQuery.value);
    }
    return {
      searchQuery,
      onSearchChange,
    };
  },
};
</script>

<style lang="postcss" scoped>
</style>