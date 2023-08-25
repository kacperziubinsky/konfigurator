<template>

    <section>
        <div class="config">
            <div class="scroll">
           
                <h2>Wybierz kategorię</h2>
                
                <div class="grid">

                    <categoryBox
                    v-for="house in houses"
                    :key="house.id"
                    :title="house.Title"
                    :id="house.ID"
                    :img="house.IMG"
                    :choose_id="choose"
                    @choosen="changeType"
                    />         



                </div>

                <h2>Wybierz Wielkość</h2>

                <div class="grid">


                    <sizeBox
                    v-for="item in houses[choose].Size"
                    :key="item"
                    :size="item"
                    :choosed_size="size"
                    @choosen_size="changeSize"
                    />

                    
                </div>

                
                <h2>Dodatki</h2>
                <div class="checkboxes">
                    <div>                    
                        <input type="checkbox" name="garage" v-model="garage" :true-value="true" :false-value="false" >
                        <label for="garage">Garaż (+15%)</label>
                    </div>

                    <div>
                        <input type="checkbox" name="warming" v-model="warming" :true-value="true" :false-value="false">
                        <label for="warming">Ocieplenie (+25%)</label>
                    </div>

                    <div>
                        <input type="checkbox" name="furniture" v-model="furniture" :true-value="true" :false-value="false">
                        <label for="furniture">Umeblowanie (+40%)</label>
                    </div>


                </div>



            </div>

            <housePrice class="sum" :type="choose" :size="size" :bonus="bonus_value"></housePrice>

        </div>

        <div class="view">
            <visualImage :choose_image="choose" class="visual"></visualImage>
        </div>
        
    </section>

</template>


<script>
import visualImage from './visualImage.vue';
import housePrice from './housePrice.vue';
import categoryBox from './categoryBox.vue';
import sizeBox from './sizeBox.vue';
export default{
    components:{
        visualImage,
        housePrice,
        categoryBox,
        sizeBox
    },
    data(){
        return{
            choose: 0,
            size: 'S',
            bonus:0,
            warming: false,
            garage: false,
            furniture: false,
            houses:[
                {ID: 0, IMG: 'https://images.prismic.io/hocomo-test/ebc29cdd-7fd1-46cb-b097-9a295a6cb6fb_138780796_1132553143863836_3687557998126616468_n+%281%29.jpg', Title: 'Do 30m²', Size: ['S', 'M', 'L', 'XL']},
                {ID: 1, IMG: 'https://images.prismic.io/hocomo-test/63ebd57a-4e29-41fb-8e46-f8d80f5159cd_Elka+z+gory+rzut_Post+OK-1111.jpg?auto=format&w=400&h=300&q=40', Title: 'Do 35m²', Size: ['S', 'M', 'L']},
                {ID: 2, IMG: 'https://images.prismic.io/hocomo-test/0c32a351-832f-4a54-8176-40f9e698c991_140707464_1637781323088517_7635965712262624082_n111111.jpg?auto=format&w=400&h=300&q=40', Title: 'Z antrsolą', Size: ['S', 'M', 'L', 'XL']},
                {ID: 3, IMG: 'https://images.prismic.io/hocomo-test/06dc3218-b583-4488-bbb3-322947b6eb4d_42m.jpg?auto=format&w=400&h=300&q=40', Title: '42m²', Size: ['S', 'M', 'L', 'XL']}
            ],
            sizes:[
                {ID: 0, S:65000, M:87000, L:95000, XL:100000 },
                {ID: 1, S:75000, M:87000, L:96400, XL:105000}
            ]
        }
    },
    methods:{
        changeType(houseID){
            this.choose=Number(houseID);
        },
        changeSize(n){
            this.size=n;
        },
        addBonus(n){
            this.bonus+=n
        },
        getSizesById(id) {
            return this.sizes.filter(size => size.ID === id);
        }
    },
    watch:{
        choose(){
            this.size='S';
            this.warming=this.garage=this.furniture=false
        },
    },
    computed:{
        bonus_value(){
            let value=0
            if(this.garage){
                value+=0.15
            }
            if(this.warming){
                value+=0.25
            }
            if(this.furniture){
                value+=0.40
            }

            return value
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


img{
    width: 100%;
    height: auto;
}
.category p,
label
{
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
label{
    font-weight: bold;
}
input[type=checkbox]{
    margin-right: 1rem;
}

</style>