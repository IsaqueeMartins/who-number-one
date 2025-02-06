<script lang="ts" setup>
import {ref} from 'vue';
import modos from '~/components/dropdown/modos.vue';
import chess from '~/components/rank/chess.vue'
</script>

<template>
    <h1 class="text-3xl text-center font-bold mt-5">Who's number one</h1>
    <modos class="mt-10"></modos>

    <chess></chess>
</template>