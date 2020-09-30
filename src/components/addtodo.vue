<template>
    <form @submit.prevent="onsubmit">
        <input type="text" v-model="title">
        <button type="submit">Add</button>
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
            onsubmit(){
                 if(this.title.trim()){
                     const newtodo ={
                         id: Date.now(),
                         title: this.title,
                         completed: false
                     }
                     
                     this.$emit('add-todo', newtodo)
                     this.title='  '
                 }
            }
    }
}
</script>>

<style scoped>
    form{
        display: flex;
    }
    input{
        width:400px;
    }
</style>