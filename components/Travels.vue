<template>
  <div class="grid grid-cols-4 gap-3">
    <div
      v-for="travel in travels"
      :key="travel.id"
      class="max-w-sm rounded overflow-hidden shadow-lg"
    >
      <img class="w-full" :src="travel.photo" alt="Sunset in the mountains" />
      <div class="px-6 py-4">
        <div class="font-bold text-xl mb-2">{{ travel.title }}</div>
        <p class="text-gray-700 text-base">
          {{ travel.description }}
        </p>
      </div>
      <div class="px-6 pt-4 pb-2">
        <span
          class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2 mb-2"
          >#photography</span
        >
        <span
          class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2 mb-2"
          >#travel</span
        >
        <span
          class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2 mb-2"
          >#winter</span
        >
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      travels: null,
    };
  },
  async created() {
    const res = await this.$axios.get(
      "https://62a7032797b6156bff84ef49.mockapi.io/api/travels"
    );
    this.travels = res.data;
  },
};
</script>

<style></style>
