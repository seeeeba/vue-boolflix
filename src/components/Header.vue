<template>
    <header>
        <input v-model="userSearchText" type="text">
        
        <button @click="$emit('searchDone',userSearchText)" >Cerca</button>
    </header>
</template>

<script>
export default {
    name: "Header",
    data:function(){
        return{
            userSearchText: ''
        };
    }
}
</script>