<template>
  <div class="searchbar-input">
    <input type="text" @input="onInput" placeholder="Search whatever you want..."/>
  </div>
</template>

<script>
export default {
  name: "SearchBar",
  methods:{
    onInput:function(event){
        this.$emit('termChange', event.target.value)
    }
 }
};
</script>

<style scoped>
  input{
    padding: 16px 40px;
    outline: none;
    border-radius: 20px;
    align-items: center;
    text-align: center;
  }
  .searchbar-input{
    display: flex;
    justify-content: center;
    margin-top: 50px;
  }
</style>
