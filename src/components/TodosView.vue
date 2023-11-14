<script setup>


import { reactive } from 'vue'
let boards = reactive([

    {
        id: crypto.randomUUID(),
        name: 'tablero 1',
        items: [
            {
                id: crypto.randomUUID(),
                title: 'Features de archivos'
            },
            {

                id: crypto.randomUUID(),
                title: 'resolver bug'
            },
        ],
    },

    {
        id: crypto.randomUUID(),
        name: 'tablero 2',
        items: [
            {
                id: crypto.randomUUID(),
                title: 'Reporte'
            },
            {

                id: crypto.randomUUID(),
                title: 'resolver otra cosa'
            },
        ],
    }


]);




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
                <div class="item" v-for="item in board.items" :key="item.id">
                    {{ item.title }}</div>
            </div>

        </div>
    </div>
</template>

<Style scoped></Style>