<template>
    <div class="container">
        <button @click="componentToRender='compHome'" class="btn btn-primary">Home</button>
        <button @click="componentToRender='compAbout'" class="btn btn-primary">About</button>
        <button @click="componentToRender='compContact'" class="btn btn-primary">Contact</button>
        <button @click="componentToRender='compAnimation'" class="btn btn-primary">Animation</button>

        <keep-alive>
            <component :is="componentToRender"></component>
        </keep-alive>

        <!-- Custom Directive- Global -->
        <!-- Assign argument -->
        <!-- <div v-awesome:red="'Hello Nazmul'"></div>
        <div v-awesome:green="'Hello Ruksi'"></div> -->
        <!-- assign modifers -->
        <div v-awesome.red.big="'Hello Nazmul'"></div>
        <div v-awesome.green.small="'Hello Ruksi'"></div>
        <hr>
        <!-- Custom Directive- Local -->
        <!-- <div v-user></div> -->
        <div v-user="userValue"></div>

        <!-- Transition-38 -->
        <transition name="appear">
            <div class="p-3 mb-2 bg-success text-white" v-if="display">How Are you?</div>
        </transition>
        
        <button @click="display=!display" class="btn btn-secondary">Toggle</button>

    </div>
</template>


<script>
import compHome from './Components/Home'
import compAbout from './Components/About'
import compContact from './Components/Contact'
import compAnimation from './Components/Animation'
export default {
    data(){
        return{
            componentToRender: 'compContact',
            userValue: "Frankey",
            display: true
        }
    },
    components:{
        compHome,
        compAbout,
        compContact,
        compAnimation
    },
    // Custom Directive- Local 
    // Properties
    directives: {
        'user':{
            bind(el,binding){
                el.innerHTML = binding.value
                el.style.color = 'Red'
            }
        }
    }
}
</script>

<style>
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