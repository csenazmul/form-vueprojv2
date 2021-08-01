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
    </div>
</template>


<script>
import compHome from './Components/Home'
import compAbout from './Components/About'
import compContact from './Components/Contact'
export default {
    data(){
        return{
            componentToRender: 'compContact'
        }
    },
    components:{
        compHome,
        compAbout,
        compContact
        }
}
</script>