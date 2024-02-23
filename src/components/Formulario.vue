<script setup>
    const props = defineProps(['valorA','valorB','operacao','fazConta'])
</script>
<template>
    <form class="d-flex gap-5 mt-5">
        <input @change="props.valorA " class="form-control fs-4" type="number">
        <select @change="props.operacao" class="form-select fs-4">
            <option value="+">+</option>
            <option value="-">-</option>
            <option value="/">/</option>
            <option value="*">*</option>
        </select>
        <input @change="props.valorB" class="form-control fs-4" type="number">
    </form>
    <h2 class="text-center mt-5">{{ props.fazConta }}</h2>
</template>