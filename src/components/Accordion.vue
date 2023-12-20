<script setup lang="ts">
import { defineProps, ref } from "vue";

defineProps(["title", "content"]);
const isExpanded = ref(false);
</script>

<template>
    <div class="accordion-container">
        <div class="inner-accordion-container">
            <h2>{{ title }}</h2>
            <button @click="isExpanded = !isExpanded" class="button-container">
                <span v-if="isExpanded">-</span>
                <span v-else>+</span>
            </button>
        </div>
        <p class="p-container" v-if="isExpanded">{{ content }}</p>
    </div>
</template>

<style scoped>
.accordion-container {
    border-radius: 5px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
    padding: 1rem;
    margin-bottom: 1.2rem;
}

.inner-accordion-container {
    display: flex;
    justify-content: space-between;
}

.p-container {
    padding-top: 0.5rem;
}

.button-container {
    width: 2rem;
    height: 2rem;
    border-radius: 50%;
    background-color: #164e63;
    color: white;
}

.button-container:hover {
    cursor: pointer;
}
</style>
