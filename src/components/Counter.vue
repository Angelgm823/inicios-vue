<template>
    <div>
        <h2>{{ customTitle}}</h2>
        <p>{{ counter }} <sup>2</sup> = {{ counter + counter }}</p>
        <p>{{ counter }} <sup>2</sup> = {{ getCuadrado() }}</p>
        <p>{{ counter }} <sup>2</sup> = {{ squareCounter }}</p>

        <div>
            <button @click="increse">+1</button>
            <button @click="decrese">-1</button>
        </div>
    </div>
</template>

<script>
    export default {
        props: ['title'],
        data(){
            return{
                counter: 15
            }
        },
        methods:{
            getCuadrado(){
                console.log('getCuadrado')
                return this.counter * this.counter
            },
            increse(){
                 this.counter++
            },
            decrese(){
                 this.counter--
            }
        },
        computed:{
            squareCounter(){
                console.log('squareCounter')
                return this.counter * this.counter
            },
            customTitle(){
                return this.title ? this.title : 'Counter';
            }
        }
    }
</script>

<style>

    button{
        background-color: aqua;
        border-radius: 5px;
        color: black;
        cursor: pointer;
        margin: 0 5px;
        transition: 0.3s ease-in-out;
    }
    button:hover{
        background-color: antiquewhite;
        transition: 0.3s ease-in-out;
    }

</style>