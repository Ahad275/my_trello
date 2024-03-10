<template>
  <div class="flex">
    <div v-for="status in statuses" :key="status.id" class="flex-1 p-4">
      <h2 class="text-xl mb-2">{{ status.title }} ({{ getStatusCount(status.id) }})</h2>
      <div class="border p-4 mb-4" @drop="handleDrop(status.id)" @dragover.prevent>
        <div v-for="card in status.cards" :key="card.id" class="mb-2 p-2 bg-gray-100" draggable="true" @dragstart="handleDragStart(card.id, status.id)">
          {{ card.title }}
        </div>
      </div>
      <button @click="addNewTask(status.id)" class="bg-blue-500 text-white p-2">+ New</button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      statuses: [
        { id: 1, title: "Not started", cards: [{ id: 1, title: "Card 1" }, { id: 2, title: "Card 2" }] },
        { id: 2, title: "In progress", cards: [{ id: 3, title: "Card 3" }] },
        { id: 3, title: "Completed", cards: [{ id: 4, title: "Card 4" }, { id: 5, title: "Card 5" }] },
      ],
    };
  },
  methods: {
    handleDragStart(cardId, statusId) {
      // Implement drag start logic
    },
    handleDrop(statusId) {
      // Implement drop logic
    },
    addNewTask(statusId) {
      // Implement adding a new task logic
    },
    getStatusCount(statusId) {
      return this.statuses.find((status) => status.id === statusId)?.cards.length || 0;
    },
  },
};
</script>

<style scoped>
/* Add your custom styles here */
</style>
