<template>
    <div class="container">
        <button @click="componentToRender='compHome'" class="btn btn-primary">Home</button>
        <button @click="componentToRender='compAbout'" class="btn btn-primary">About</button>
        <button @click="componentToRender='compContact'" class="btn btn-primary">Contact</button>

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

    </div>
</template>


<script>
import compHome from './Components/Home'
import compAbout from './Components/About'
import compContact from './Components/Contact'
export default {
    data(){
        return{
            componentToRender: 'compContact',
            userValue: "Frankey"
        }
    },
    components:{
        compHome,
        compAbout,
        compContact
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