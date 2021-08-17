<template>
  <div>
    <p class="pt-4 text-gray-600 border-t">
      Example of a component using the composition API syntax.
    </p>
    <p class="pt-4 text-gray-600">
      The button styles are used from the global styles in
      <code class="inline-code">assets/css/tailwind.css</code>
    </p>
    <div class="flex items-center mt-4 ml-2">
      <button class="btn" @click="decreaseCounter">Decrease</button>
      <button class="ml-2 btn" @click="increaseCounter">Increase</button>
      <p class="ml-4 font-semibold text-blue-600">count is: {{ count }}</p>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from '@nuxtjs/composition-api';

export default defineComponent({
  setup() {
    const count = ref(0);

    const decreaseCounter = () => {
      count.value--;
    };

    const increaseCounter = () => {
      count.value++;
    };

    return { count, decreaseCounter, increaseCounter };
  },
});
</script>

<style lang="postcss" scoped>
.btn2 {
  @apply px-4 py-2
        font-medium tracking-wide text-white capitalize
        transition-colors duration-200 transform
        rounded-md
        bg-blue-600 hover:bg-blue-500 
        focus:outline-none focus:bg-blue-500;
}
</style>
