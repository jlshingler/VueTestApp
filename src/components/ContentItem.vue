<script setup>
    /* Accepts prop to vary styling */
    defineProps({
        swap: {
            type: Boolean,
            required: true,
            default: false
        }
    })
</script>

<template>
    <div v-if=swap class="item container-xxl"> <!-- v-if statement to vary styling based on props -->
        <div class="row">
            <div class="details col col-sm-8 col-12 order-2 order-sm-1">
                <slot name="details"></slot>
            </div>
            <div class="title col col-sm-4 col-12 order-1 order-sm-2">
                <h2>
                    <slot name="title"></slot>
                </h2>
            </div>
        </div>
    </div>
    <div v-else class="item container-xxl">
        <div class="row">
            <div class="title col col-sm-4 col-12">
                <h2>
                    <slot name="title"></slot>
                </h2>
            </div>
            <div class="details col col-sm-8 col-12">
                <slot name="details"></slot>
            </div>
        </div>
    </div>
</template>

<style scoped>
    .item {
        display: grid;
        padding: 50px 25px;
    }

    .title {
        text-align: center;
    }
</style>
