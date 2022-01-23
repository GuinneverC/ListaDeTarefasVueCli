<template>
    <input @keyup.enter="$emit('salvar')" @keyup="$emit('input', valorInterno)" type="text" v-model="valorInterno">
</template>

<script>
export default {
    props: ['value'],
    data() {
        return {
            valorInterno: this.value,
        }
    }
}
</script>

<style>


</style>