<template>
  <div id="app">
    <h1>Vue J.S Multilingual App using vue i18n</h1>
    <img alt="Vue logo" src="./assets/logo.png">
    <br><br>
    <select @change="doMultilingual" v-model="inputlang">
      <option value="chooselang"  disabled>Change Language</option>
      <option value="eng">English</option>
      <option value="hin">Hindi</option>
      <option value="pub">Punjabi</option>

    </select>
    <h1>{{$t('welcomemsg')}}</h1>
    <h2>{{$t('msg')}}</h2>

  </div>
</template>

<script>

export default {
  name: 'App',
  components: {
  },
  data(){
    return{
      inputlang: 'eng'
    }
  },
  methods:{
    doMultilingual(){
      if(this.inputlang == 'eng' ){
        this.$i18n.locale = "en";
      } 
      if(this.inputlang == 'hin' ){
        this.$i18n.locale = "hi";
      }

      if(this.inputlang == 'pub' ){
        this.$i18n.locale = "pb";
      }

      }
    }
  
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
select{
  padding: 10px;
  font-weight: bold;
  font-size: 1.1rem;
  border-radius: 30px;
}
select:focus{
  outline: none;
}
</style>
