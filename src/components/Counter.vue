<template>
    <h2>{{customTitle}}</h2>
    <p>{{counter}} <sup>2</sup> = {{counter * counter}}</p>
    
    <div>
        <button @click="increase">+1</button>
        <button @click="decrease">-1</button>
    </div>
</template>

<script>
    export default{
        props:{
            titulo: String,
            start: {
                type: Number,
                default: 10,
                validator(value){
                    return value > 100
                } 
            }
        },
        //name: 'Patito
        data(){
            return{
                counter: this.start,
            }
        },
        methods:{
            getSquareCounter(){
                return this.counter * this.counter
            },
            increase(){
                this.counter = this.counter + 1
            },
            decrease(){
                this.counter = this.counter - 1
            }
        },
        computed: {
            squareCounter(){
                console.log('computed square counter')
                return this.counter * this.counter
            },
            customTitle(){
                return this.titulo ? this.titulo  : 'Counter'
            }
        }
    }
</script>

<style>
    button{
        background-color: #64BB87;
        color: white;
        margin: 0 5px;
    }
</style>