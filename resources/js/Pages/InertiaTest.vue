<script setup>
import { Link } from "@inertiajs/vue3";
import { ref } from "vue";

const newTitle = ref('');
const newContent = ref('');
</script>

<template>
    Inertiaテストです。<br>
    <a href="/">aタグ経由です。</a><br>
    <Link href="/">Link経由です。</Link><br>
    <Link v-bind:href="route('inertia.index')">名前付きルートの確認</Link><br>
    <Link v-bind:href="route('inertia.show', { id: 1 })">ルートパラメータのテストです</Link>
    <div class="mb-8"></div>
    <input type="text" name="newTitle" v-model="newTitle"><br>
    <input type="text" name="newContent" v-model="newContent"><br>
    <Link as="button" method="post" v-bind:href="route('inertia.store')" v-bind:data="{ title: newTitle, content: newContent }">DB保存テスト</Link>
</template>