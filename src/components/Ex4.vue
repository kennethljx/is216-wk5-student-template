<script setup>
import { ref } from 'vue'
const items = ref(['keyboard', 'mouse', 'iPhone', 'macbook', 'adapter'])

// TODO: Add Code Here
function deleteItem (index) {
    items.value.splice(index,1)
}

const newItem = ref('');
function addItem(item) {
    items.value.push(item)
    newItem.value = ""
}

</script>

<template>

    <h2>Shopping Cart</h2>
    <!-- TODO: Add Code Here -->
    <ul>
        <li v-for="(item, index) in items">
            {{ item }}
            <button @click="deleteItem(index)">Delete</button>
        </li>
    </ul>
    <input type="text" v-model.trim="newItem" v-on:keyup="addItem(newItem)">
    <button @click="addItem(newItem)" >Add!</button>
   
</template>

<!--  -->