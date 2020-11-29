<template>
    <div class="flex items-center">
        <div class="flex flex-col items-center justify-between space-y-1">
            <span
                class="text-red-800 text-3xl md:text-4xl w-16 h-16 md:w-24 md:h-24 flex items-center justify-center border rounded-md border-gray-400 rounded-md shadow-md"
            >
                {{ number }}
            </span>
            <span class="text-xs text-red-800">{{ label }}</span>
        </div>
    </div>
</template>
<script>
export default {
  props: ['number', 'label']
}
</script>
