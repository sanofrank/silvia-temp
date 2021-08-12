<template>
    <div id="title" :class="classes">
        {{ title.toUpperCase() }}
    </div>
</template>


<script>
export default {
    props: ['title', 'classes']
}
</script>

<style lang="scss" scoped>
    #title {
        font-family: "Silvia Font" !important;
    }
</style>