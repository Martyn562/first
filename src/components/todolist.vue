<template>
    <div>
        <ul>
            <todoitem 
                v-for="(todo, i) in todos" v-bind:key="todo"
                v-bind:todo="todo"
                v-bind:index="i"
                @remove-todo="removetodo"
            />
        </ul>
    </div>
</template>

<script>
import todoitem from '@/components/todoitem'
export default{
    props: ['todos'],
    components: {
        todoitem
    },
    methods: {
        removetodo(id){
            this.$emit('remove-todo', id)
        }
    }
}
</script>