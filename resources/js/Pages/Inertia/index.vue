<script setup>
import { Link } from '@inertiajs/vue3';
import { ref } from 'vue';
    defineProps({
        blogs: Array
    })
</script>

<template>
    <div v-if="$page.props.flash.message" class="bg-blue-300">
        {{ $page.props.flash.message }}
    </div>
    <ul>
        <li v-for="blog in blogs" :key="blog.id">
            件名： <Link :href="route('inertia.show', { id: blog.id})" class="text-blue-300">{{ blog.title }}</Link>
            本文：{{ blog.content }}
        </li>
    </ul>
</template>
