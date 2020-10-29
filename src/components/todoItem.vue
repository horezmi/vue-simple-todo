<template>
    <li>
        <span v-bind:class="{done: todo.completed}">
            <input type="checkbox" 
                v-on:change="todo.completed = !todo.completed">
            <strong> {{index + 1}} </strong>
            {{todo.title}}
        </span>
        <button class="remove"
            v-on:click="$emit('remove-todo', todo.id)">&times;</button>
    </li>
</template>

<script>
export default {
    props: {
        todo: { 
            type: Object,
            required: true
        },
        index: Number
    }
}
</script>

<style scoped>
    li {
        border: 1px solid #ccc;
        display: flex;
        justify-content: space-between;
        padding: .5rem 2rem;
        margin-bottom: 1rem;
    }
    .remove {
        background: #41b883;
        color: #fff;
        border-radius: 50%;
        width: 30px;
        height: 30px;
        font-weight: bold; 
    }
    input {
        margin-right: 1rem;
        background: #41b883;
    }
    span {
        font-weight: 700;
        font-size: 18px;
    }
    .done {
        text-decoration: line-through;
    }
</style>