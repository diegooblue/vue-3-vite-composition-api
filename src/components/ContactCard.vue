<template>
  <div class="mt-4">
    <img
      class="rounded border-solid"
      :src="contact.picture.medium"
      :alt="`Photo of ${fullName}`"
    />
    <div>
      <h1>{{ fullName }}</h1>
      <p>{{ contact.phone }}</p>
      <p>{{ location }}</p>
      <p>{{ contact.email }}</p>
    </div>
  </div>
</template>

<script>
import { computed } from "vue";
export default {
  props: { contact: Object },
  setup(props) {
    const fullName = computed(
      () => `${props.contact?.name?.first} ${props.contact?.name?.last}`
    );
    const location = computed(
      () =>
        `${props.contact?.location?.city},  ${props.contact?.location?.country}`
    );
    return { fullName, location };
  },
};
</script>