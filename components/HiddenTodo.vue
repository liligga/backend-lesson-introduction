<script setup lang="ts">
    import { ref } from 'vue'

    const marked = ref<Number[]>([])

    const props = defineProps({
        todos: Array
    })

    const showTodo = (index: number) => {
        if (index === 0) return true
        let result = true
        for (let i = 0; i < index; i++) {
            if (!marked.value.includes(i)) {
                result = false
                break
            }
        }
        return result
    }

    const toggleTodo = (index: number) => {
        if(marked.value.includes(index)) {
            console.log(marked.value, "remove", index)
            marked.value.splice(marked.value.indexOf(index), 1)
        }
        else {
            console.log(marked.value, "add", index)
            marked.value.push(index)
        }
    }
</script>

<template>
    <div>
        <ul 
            flex="~ col gap-4"
            v-for="(todo, index) in props.todos"
            :key="index"
        >
            <li 
                class="flex gap-2"
                v-if="showTodo(index)"
            >
                <input
                    @click="toggleTodo(index)"
                    value="{{ index }}"
                    type="checkbox"
                    :checked="marked.includes(index)"
                />
                <span
                    @click="toggleTodo(index)"
                >{{ todo }}</span>
            </li>

        </ul>
    </div>

</template>

<style scoped>
    li span, li input {
        cursor: pointer;
    }
</style>