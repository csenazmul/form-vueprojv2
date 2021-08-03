<template>
    <div class="container">
        Transition
        <transition 
            name="appear"
            enter-active-class="animated slideInDown"
            leave-active-class="animated slideInUp">
            <div class="p-3 mb-2 bg-success text-white" v-if="display">How Are you?</div>
        </transition>
        
        <button @click="display=!display" class="btn btn-secondary">Toggle</button>

    </div>

</template>

<script>
    export default {
        data () {
            return {
                display: false
            }
        }
    }
</script>

<style scoped>
    .appear-enter{
        opacity: 0;
    }
    .appear-enter-active{
        transition: opacity 3s;
    }
    .appear-leave{

    }
    .appear-leave-active{
        opacity: 0;
        transition: opacity 3s;
    }
</style>