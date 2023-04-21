<template>
    <div  >
        <div>
      <p  v-for="(user,i) in users" :key="i" @click="user_clicked" :users="user">{{ user}}</p>

    </div>
    <special-user :userName="userName"></special-user>
    </div>
</template>

<script>
import SpecialUser from '@/components/SpecialUser.vue'
export default {
    components:{
            SpecialUser
        },
        data() {
            return {
                userName:undefined,
                users: [`Lula`,`lulu`,`lemlem`]
            }
    },
    methods: {
        user_clicked(details){
            let userName = details[`target`].getAttribute( `users` );
            this.userName=userName
            }
    },
    highlight_username() {
       this.$root.$emit(`highlight_username`, this.userName);
},

}
</script>

<style scoped>

</style>