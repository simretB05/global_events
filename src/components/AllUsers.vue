<template>
    <div>
        <div v-for="(usersdata,i) in dataresponses" :key="i">
<h1>{{ usersdata[`first_name`] }}</h1>
<p>{{usersdata[`email`]}}</p>
<p>{{usersdata[`last_name`]}}</p>

<img :src="usersdata[`avatar`]" alt="song album image">


    </div>
</div>
</template>

<script>
    import axios from "axios";

export default {
    data() {
        return {
            dataresponses: undefined,
            errorData:undefined
        }
    },
    mounted(){
        axios.request({
            url: `https://reqres.in/api/users`
        } ).then( ( response ) =>{
            this.dataresponses = response[`data`][`data`]
            
        } ).catch(( error) =>{
this.errorData=error
        } )
    }
    }
</script>

<style scoped>

</style>