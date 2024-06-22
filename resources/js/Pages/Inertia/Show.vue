<script setup>
import { router } from '@inertiajs/vue3'
defineProps({
    id : String,
    blog : Object,
})

const deleteConfirm = (id) => {
    router.delete(`/inertia/${id}`,{
        onBefore: () => confirm('本当に削除しますか？')
    })
}
</script>

<template>
{{ id }}
{{ blog.title }}
<button @click="deleteConfirm(blog.id)" class="bg-blue-200">削除</button>
</template>
