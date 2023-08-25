<template>
    
    <h3>Suma: {{ forrmatedPrice }} zł {{ bonus_price }}</h3>

</template>

<script>
export default{
    props:['type', 'size','bonus'],
    computed: {
        price() {
            /* 30m2 */
            if(this.type===1){
                    if(this.size==='S'){
                        return Number('65000');
                    } else if(this.size==='M'){
                        return  Number('87000');
                    } else if(this.size==='L'){
                        return  Number('95000');
                    } else if (this.size==='XL'){
                        return  Number('100000');
                    } else{
                        return 'EROR'
                    }
                } else  if(this.type===2){
                    if(this.size==='S'){
                        return Number('75000');
                    } else if(this.size==='M'){
                        return Number('87000');
                    } else if(this.size==='L'){
                        return Number('96400');
                    } else if (this.size==='XL'){
                        return Number('105000');
                    } else{
                        return 'EROR'
                    }
                } else  if(this.type===3){
                    if(this.size==='S'){
                        return Number('66000');
                    } else if(this.size==='M'){
                        return Number('78000');
                    } else if(this.size==='L'){
                        return Number('93400');
                    } else if (this.size==='XL'){
                        return Number('111000');
                    } else{
                        return 'EROR'
                    }
                } else  if(this.type===4){
                    if(this.size==='S'){
                        return Number('92000');
                    } else if(this.size==='M'){
                        return Number('102000');
                    } else if(this.size==='L'){
                        return Number('112400');
                    } else if (this.size==='XL'){
                        return Number('123230');
                    } else{
                        return 'EROR'
                    }
                }
                else {
                    return 'ERROR'
                }     
        },
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