<template>
    
    <h3>Suma: {{ forrmatedPrice }} zł {{ bonus_price }}</h3>

</template>

<script>
export default{
    props:['price','bonus'],
    computed: {
        bonus_price(){
            const bonus=this.price*this.bonus;
            const value=Math.round(bonus);
            if(value>0){
                return '+ ' + value.toLocaleString() + ' zł';
            } else{
                return '';
            }
        },
        forrmatedPrice(){
            return this.price.toLocaleString();
        }
    }
}
</script>