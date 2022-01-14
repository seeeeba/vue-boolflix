<template>
    <header>
        <div class="container">

            <div class="logo">
                Boolflix
            </div>
            <div class="button">
                <input v-model="userSearchText" type="text" placeholder="Titoli, persone, genere">        
                <button @click="$emit('searchDone',userSearchText)" >Cerca</button>
            </div>
        </div>
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

<style lang="scss" scoped>

header{
    background-color: #383838;
    padding: 20px 0;
    border-bottom: 1px solid black;
}

.container{
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 0 20px;
}

.logo{
    text-transform:uppercase;
    font-size: 40px;
    color: red;
}

.button input{ 
    width: 250px;
    padding: 5px;       
}

.button button {
    margin-left: 10px;
    padding: 5px;
}

</style>