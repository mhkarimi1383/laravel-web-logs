<template>
    <div @click="$emit('close')" class="fixed inset-0 w-full h-full bg-black bg-opacity-75 z-20 overflow-auto">
        <div @click.stop class="mx-auto w-full max-w-lg bg-white my-24 rounded-lg p-6 space-y-10">
            <slot></slot>
        </div>
    </div>
</template>
<script>
import {defineComponent} from "vue";

export default defineComponent({
    name : 'Modal',
    created() {
        document.body.style.overflow = 'hidden'
    },
    unmounted() {
        document.body.style.overflow = 'auto'
    },
    emits: ['close']
})
</script>
