<template>
    
    <h3>Suma: {{ price }} </h3>

</template>

<script>
export default{
    props:['type', 'size'],
    computed: {
        price() {
            /* 30m2 */
            if(this.type===1){
                    if(this.size==='S'){
                        return '65 000zł'
                    } else if(this.size==='M'){
                        return '87 000zł'
                    } else if(this.size==='L'){
                        return '95 000zł'
                    } else if (this.size==='XL'){
                        return '100 000zł'
                    } else{
                        return 'EROR'
                    }
                } else  if(this.type===2){
                    if(this.size==='S'){
                        return '75 000zł'
                    } else if(this.size==='M'){
                        return '87 000zł'
                    } else if(this.size==='L'){
                        return '96 400zł'
                    } else if (this.size==='XL'){
                        return '105 000zł'
                    } else{
                        return 'EROR'
                    }
                } else  if(this.type===3){
                    if(this.size==='S'){
                        return '66 000zł'
                    } else if(this.size==='M'){
                        return '78 000zł'
                    } else if(this.size==='L'){
                        return '93 400zł'
                    } else if (this.size==='XL'){
                        return '111 000zł'
                    } else{
                        return 'EROR'
                    }
                } else  if(this.type===4){
                    if(this.size==='S'){
                        return '92 000zł'
                    } else if(this.size==='M'){
                        return '102 000zł'
                    } else if(this.size==='L'){
                        return '112 400zł'
                    } else if (this.size==='XL'){
                        return '123 230zł'
                    } else{
                        return 'EROR'
                    }
                }
                else {
                    return 'ERROR'
                }     

        }
    }
}
</script>