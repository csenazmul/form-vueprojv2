<template>
    <div class="container">
        <button @click="componentToRender='compHome'" class="btn btn-primary">Home</button>
        <button @click="componentToRender='compAbout'" class="btn btn-primary">About</button>
        <button @click="componentToRender='compContact'" class="btn btn-primary">Contact</button>

        <keep-alive>
            <component :is="componentToRender"></component>
        </keep-alive>
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