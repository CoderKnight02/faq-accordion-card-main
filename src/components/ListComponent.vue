<script>
    export default{
        data(){
            return{
                rot: false,
                show: false
            }
        },  
        props:{
            lista: Object,
            index: Number
        },
        methods:{
            event(){
                this.rot = !this.rot
                this.show = !this.show
            }
        }

    }
</script>


<template>
    <div class="lista">
        <div class="header">
            <dt>{{lista.header}}</dt>
            <button @click="event" :class="{'rotate': rot}"><img src="../assets/images/icon-arrow-down.svg" alt="*"></button>
        </div>
        <transition name="fade">
            <dd v-show="show">{{lista.description}}</dd>
        </transition>
    </div>
        
</template>


<style scoped>

    .header{
        display: flex;
        justify-content: space-between;
    }
    .lista{
        border-bottom: 1px solid hsl(240, 5%, 91%);
        padding: 15px;
        color: hsl(240, 6%, 50%);
    }

    .show{
        overflow: hidden;
        height: 0;
    }
    
    dd{
        margin: 0;
        margin-top: 10px;
        padding-right: 30px;
        
    }

    button{
        transition: .3s;
        background-color: transparent;
        border: none;
    }

    .rotate{
        transform: rotate(-180deg);
    }

    .fade-enter-active, .fade-leave-active {
        transition: opacity .2s
    }
    .fade-enter, .fade-leave-to {
        opacity: 0
    }


</style>