<template>
    <div>
<h1>{{ userName }}</h1>
    </div>
</template>

<script>
    export default {
    props: {
        userName: String
}
        
    }
</script>

<style scoped>

h1{
    background-color: red;
    color: rgb(0, 255, 13);
}
</style>