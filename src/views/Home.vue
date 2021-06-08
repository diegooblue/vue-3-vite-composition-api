<template>
  <div class="">
    <ContactHeader @search="searchContact" />
    <div class="grid grid-cols-4 gap-5 overflow-auto h-80">
      <ContactCard
        v-for="(contact, idx) in filteredContacts"
        :key="contact.name.first + idx"
        :contact="contact"
      />
    </div>
  </div>
</template>

<script>
import ContactHeader from "../components/ContactHeader.vue";
import ContactCard from "../components/ContactCard.vue";
import useContacts from "../hooks/UseContacts.js";

export default {
  components: { ContactHeader, ContactCard },
  setup() {
    const { isLoading, search, filteredContacts } = useContacts();
    function searchContact(query) {
      search.value = query;
    }
    return {
      search,
      filteredContacts,
      searchContact,
      isLoading,
    };
  },
};
</script>

<style>
</style>