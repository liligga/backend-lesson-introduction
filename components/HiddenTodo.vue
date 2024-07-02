<script setup lang="ts">
    import { ref } from 'vue'

    const marked = ref([])

    const props = defineProps({
        todos: Array
    })
</script>

<template>
    <div>
        <ul 
            flex="~ col"
            v-for="(todo, index) in props.todos"
            :key="index"  
        >
            <li v-if="index === 0 || (marked.includes(index-1))">
                <input type="checkbox"
                    :on-click="marked.push(index)" />
                <span>{{ todo }}</span>
            </li>

        </ul>
    </div>

</template>