<script setup>
import { ref } from 'vue';

const expanded = ref(false);

function click() {
  expanded.value = !expanded.value;
}

defineProps({
  name: {
    type: String,
    required: true
  },
  bio: {
    type: String,
    required: false
  },
  contact: {
    type: Array,
    required: false
  }
});
</script>

<template>
  <div class="greetings">
    <h3 @click="click" class="green">{{ name }}</h3>
    <p v-if="expanded">
      {{ bio }}
    </p>
  </div>
</template>

<style scoped>
h1 {
  font-weight: 500;
  font-size: 2.6rem;
  top: -10px;
}

h3 {
  font-size: 1.2rem;
}

.greetings h1,
.greetings h3 {
  text-align: center;
}

@media (min-width: 1024px) {
  .greetings h1,
  .greetings h3 {
    text-align: left;
  }
}
</style>