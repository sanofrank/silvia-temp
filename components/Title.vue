<template>
    <div :class="classes"> <!--id="title" -->
        {{ title.toUpperCase() }}
    </div>
</template>


<script>
export default {
    props: ['title', 'classes']
}
</script>

<style lang="scss" scoped>
    // #title {
    //     font-family: "Silvia Font" !important;
    // }
</style>