<script lang="ts">
import { defineComponent } from "vue";
import Vue3StarRatings from "@/vue3-star-ratings.vue";

export default defineComponent({
  name: "ServeDev",
  components: {
    Vue3StarRatings,
  },
  data() {
    return {
      rate: 4.2,
    };
  },
  methods: {
    updateRating (e: any) {
      console.info('teste update action - ', e)
    }
  }
});
</script>

<template>
  <div id="app">
    <p style="text-align: center; font-size: 3rem">
      {{ rate }}
    </p>
    <vue3-star-ratings
      v-model="rate"
      :step="0.5"
      :starSize="'34'"
      :disableClick="false"
      :controlSize="'23'"
      inactiveColor="deeppink"
      starColor="blue"
      @update:modelValue="updateRating"
    />
  </div>
</template>
