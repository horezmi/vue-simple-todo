<template>
    <form @submit.prevent="onSumbit"> 
        <input tyoe="text" v-model="title">
        <button type="sumbit">Create</button>
    </form>
</template>

<script>
export default {
    data() {
        return {
            title: ''
        }
    },
    methods: {
        onSumbit() {
            console.log('Submit', this.title);
            if (this.title.trim()) {
                const newTodo = {
                    id: Date.now(),
                    title: this.title,
                    completed: false,
                }
                this.$emit('add-todo', newTodo)
                this.title =''
            }
        }
    }
}
</script>

<style scoped>
    input {
        background: #41b883;
        font-weight: 700;
        font-size: 18px;
    }
    button {
        background: #35495e;
        font-weight: 700;
        font-size: 20px;
        color: white;
        width: 100px;
        height: 35px;
    }
    form {
        display: flex;
    }
    input {
        width: 100%;
    }
</style>