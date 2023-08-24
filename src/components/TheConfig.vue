<template>

    <section>
        <div class="config">
            <div class="scroll">
           
                <h2>Wybierz kategorię</h2>
                
                <div class="grid">

                    <div class="category" @click="changeType(1)" :class="choose===1 ? 'active' : ''">
                        <img src="https://images.prismic.io/hocomo-test/ebc29cdd-7fd1-46cb-b097-9a295a6cb6fb_138780796_1132553143863836_3687557998126616468_n+%281%29.jpg?auto=format&w=400&h=300&q=40" alt="">
                        <p>Do 30m²</p>
                    </div>

                    <div class="category"  @click="changeType(2)" :class="choose===2 ? 'active' : ''">
                        <img src="https://images.prismic.io/hocomo-test/63ebd57a-4e29-41fb-8e46-f8d80f5159cd_Elka+z+gory+rzut_Post+OK-1111.jpg?auto=format&w=400&h=300&q=40" alt="">
                        <p>Do 35m²</p>
                    </div>

                    <div class="category"  @click="changeType(3)" :class="choose===3 ? 'active' : ''">
                        <img src="https://images.prismic.io/hocomo-test/0c32a351-832f-4a54-8176-40f9e698c991_140707464_1637781323088517_7635965712262624082_n111111.jpg?auto=format&w=400&h=300&q=40" alt="">
                        <p>Z antrsolą</p>
                    </div>

                    <div class="category"  @click="changeType(4)" :class="choose===4 ? 'active' : ''">
                        <img src="https://images.prismic.io/hocomo-test/06dc3218-b583-4488-bbb3-322947b6eb4d_42m.jpg?auto=format&w=400&h=300&q=40" alt="">
                        <p>42m²</p>
                    </div>
                </div>

                <h2>Wybierz Wielkość</h2>

                <div class="grid">

                    <div class="category" @click="changeSize('S')" :class="size==='S' ? 'active' : ''" >
                        <p>S</p>
                    </div>

                    <div class="category" @click="changeSize('M')" :class="size==='M' ? 'active' : ''" >
                        <p>M</p>
                    </div>

                    <div class="category" @click="changeSize('L')" :class="size==='L' ? 'active' : ''" >
                        <p>L</p>
                    </div>

                    <div class="category" @click="changeSize('XL')" :class="size==='XL' ? 'active' : ''" >
                        <p>XL</p>
                    </div>

                </div>
                

            </div>

            <housePrice class="sum" :type="choose" :size="size"></housePrice>

        </div>

        <div class="view">
            <visualImage :choose_image="choose" class="visual"></visualImage>
        </div>
        
    </section>

</template>


<script>
import visualImage from './visualImage.vue';
import housePrice from './housePrice.vue';
export default{
    components:{
        visualImage,
        housePrice
    },
    data(){
        return{
            choose: 1,
            size: 'S',

        }
    },
    methods:{
        changeType(n){
            this.choose=n;
        },
        changeSize(n){
            this.size=n;
        }
    },
    watch:{
        choose(){
            this.size='S';
        }
    },
    computed:{
        full() {
            return this.choose + ' ' + this.size;
            }
    }
}


</script>



<style scoped>
section{
    display: flex;
    flex-direction: row-reverse;
    height: 90vh;
}
.config{
    width: 30%;
    background-color: white;
    display: flex;
    flex-direction: column;
}
.sum{
    background-color: black;
    width: 100%;
    align-self: flex-end;
    text-align: center;
    color: white;
    padding: 1rem;
    font-size: 1.5rem;
}

h2{
    text-align: center;
}

.view{
    width: 70%;
    height: 80vh;
    text-align: center;
    margin-top: 5vh
}

.grid{
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
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
.category p{
    font-size: 1.25rem;
    line-height: 1.6;
}
.scroll{
    overflow: auto;
    height:100vh;
    padding: 2rem;
}
.active{
    border: 1px solid black;
}
.visual{
    height: 100%;
    width: auto;
    box-shadow: rgba(0, 0, 0, 0.2) 0px 2px 1px -1px, rgba(0, 0, 0, 0.14) 0px 1px 1px 0px, rgba(0, 0, 0, 0.12) 0px 1px 3px;
    border: 2px solid rgba(255, 255, 255, 0);
}

</style>