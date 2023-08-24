<template>
    <img :src="imageUrl" alt="">
</template>

<script>
export default{
    props:['choose_image'],
    data(){
        return{
            imageUrl:'https://images.prismic.io/hocomo-test/ebc29cdd-7fd1-46cb-b097-9a295a6cb6fb_138780796_1132553143863836_3687557998126616468_n+%281%29.jpg'
        }
    },
    watch:{
        choose_image(){
            if(this.choose_image===1){
                this.imageUrl="https://images.prismic.io/hocomo-test/ebc29cdd-7fd1-46cb-b097-9a295a6cb6fb_138780796_1132553143863836_3687557998126616468_n+%281%29.jpg"
            }
            if(this.choose_image===2){
                this.imageUrl="https://images.prismic.io/hocomo-test/63ebd57a-4e29-41fb-8e46-f8d80f5159cd_Elka+z+gory+rzut_Post+OK-1111.jpg"
            }
            if(this.choose_image===3){
                this.imageUrl="https://images.prismic.io/hocomo-test/0c32a351-832f-4a54-8176-40f9e698c991_140707464_1637781323088517_7635965712262624082_n111111.jpg"
            }
            if(this.choose_image===4){
                this.imageUrl="https://images.prismic.io/hocomo-test/06dc3218-b583-4488-bbb3-322947b6eb4d_42m.jpg"
            }
        }
    }
}
</script>