<script>
export default { 
    data() {
        return {
            items: ['keyboard', 'mouse', 'iPhone', 'macbook', 'adapter'],
            newItem: ""
        }
    },
    methods: {
        addItem() {
            this.items.push(this.newItem)
            this.newItem = "" // optional: clears the input after adding
        }
    }
}
</script>

<template>
    <h2>Shopping Cart</h2>
    <ul>
        <li v-for="(item, idx) in items">
            {{ item }} <button @click="items.splice(idx, 1)">Delete!</button>
        </li>
    </ul>
    <input type="text" v-model="newItem"/>
    <button @click="addItem">Add!</button>
</template>
