<script setup>
import { reactive } from "vue";
import InputNew from "./InputNew.vue";

let boards = reactive([
  {
    id: crypto.randomUUID(),
    name: "tablero 1",
    items: [
      {
        id: crypto.randomUUID(),
        title: "Features de archivos",
      },
      {
        id: crypto.randomUUID(),
        title: "resolver bug",
      },
    ],
  },
  {
    id: crypto.randomUUID(),
    name: "tablero 2",
    items: [
      {
        id: crypto.randomUUID(),
        title: "Reporte",
      },
      {
        id: crypto.randomUUID(),
        title: "resolver otra cosa",
      },
    ],
  },
]);

function handleNewItem(text) {
  console.log(text);
}
</script>

<template>
  <nav>
    <ul>
      <li><a href="#">Create Board</a></li>
    </ul>
  </nav>

  <div class="boards-container">
    <div class="boards">
      <div class="board" v-for="board in boards" :key="board.id">
        <div>{{ board.name }}</div>

        <InputNew :on-new-item="handleNewItem" />

        <div class="items">
          <div class="item" v-for="item in board.items" :key="item.id">
            {{ item.title }}
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.drop-zone {
  background-color: #eee;
  margin-bottom: 10px;
  padding: 10px;
}
.drag-el {
  background-color: #fff;
  margin-bottom: 10px;
  padding: 5px;
}

.boards {
  display: flex;
  gap: 10px;
}

.board {
  background: #ccc;
  padding: 10px;
}
.items {
  display: flex;
  flex-direction: column;
  gap: 5px;
}

.item {
  background: white;
  padding: 10px;
  box-sizing: border-box;
}
</style>
