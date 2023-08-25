<template>
        <div class="category" :class="id===choose_id ? 'active' : ''" @click="emition" >
                <img :src="img" :alt="title">
                <p>{{ title }}</p>
        </div>
</template>

<script>
export default{
    props: ['id', 'choose_id', 'img', 'title'],
    methods:{
        emition() {
            this.$emit('choosen', this.id);
        }
    }
}

</script>

<style>
.active{
    border: 1px solid black;
}
.category{
    box-shadow: rgba(0, 0, 0, 0.2) 0px 2px 1px -1px, rgba(0, 0, 0, 0.14) 0px 1px 1px 0px, rgba(0, 0, 0, 0.12) 0px 1px 3px;
    border: 2px solid rgba(255, 255, 255, 0);
    cursor: pointer;
    padding: 1rem;
    margin: 1rem;
}
img{
    width: 100%;
    height: auto;
}

</style>