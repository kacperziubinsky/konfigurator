<template>

        <div class="category" :class="size===choosed_size ? 'active' : ''" @click="emition">
            <p>{{ size }} </p>
        </div>

</template>


<script>
export default{
    props:['size', 'choosed_size'],
    methods:{
        emition() {
            this.$emit('choosen_size', this.size);
        }
    }
}
</script>


<style scoped>

</style>