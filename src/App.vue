<template>
<div id="app">
    <Logo bienvenue="Message de bienvenue" v-on:sendBounce="bounces ++" :bounces="bounces"/>
    <h1>Intro à Vue.js</h1>
    <div class="counter">
         Counter :{{counter}}
    </div>
    <button @click='clicked' class="clicks">
          Clicks :{{clicks}}
    </button>
    <div id="conditional">
      <span v-if="clicks>=10">calme</span>
    </div>
    <h2> {{message}} </h2>
    <input v-model="message"/>
    <ul id="array-rendering">
    <li v-for="item in items" :key='item.name' @click='test'>
      {{item.name}}only for {{item.price}}
    </li>
    </ul>


</div>
</template>

<script>

import Logo from './components/Logo' 

export default {
  name: 'App',
  components: {
    Logo,
      },
  data(){
    return{
      counter:0,
      clicks:0,
      message: "Salut !",

      items: [
        {name :  'TV LG15ED56 4K', price:"899€"},
        {name :  'Sony Playstation 5', price:"599€"},
        {name :  'Xbox Series X', price:"499€"},
        {name :  'Apple iPhone 12', price:"999€"},
        {name :  'samsung Galaxy S21', price:"899€"},
        {name :  'TV Samsung 1H 4K', price:"999€"}
      ],
     bounces:0,

    }
  },
  mounted(){
    setInterval(()=>{
      this.counter++
    },1000)
  },
  methods :{
    clicked(){
      this.clicks++;
    },
    test(){
      console.log(this)
    },
    


  }
}

</script>

<style>

*{
    list-style: none;
    text-align: center;
    font-family: Avenir, Helvetica, Arial, sans-serif;
    margin: 5px;
    padding: 0;
}
ul{
  transform: translateX(25%);
  width: 15%;
  margin: auto;
}
li{
  text-align: left;
}
li:hover{
  background-color:black;
  color: white;
  transition: all 0.5s ease;
  cursor: pointer;
}
.blue{
  font-size:3rem ;
}


</style>
