<template>
  <div class="test">
      <input type="text" v-model="title"></br>
      <h1>{{title}}</h1>
      <p v-if="showName">{{user.firstName}}</p>
      <ul>
          <li v-for="item in items">{{item.title}}</li>
      </ul>
      <button v-on:click="greet('Hello Karan')">Say Greetings</button>
      </br>
      <input type="text" v-on:keyup="pressKey" v-on:keyup.enter="enterHit">
      </br>
      <label>First Name:</label><input type="text" v-model="user.firstName">
      </br>
      
    <label>Last Name:</label><input type="text" v-model="user.lastName">
    </br>

  </div>
</template>

<script>
 export default {
     name:'test',
     data() {
         return {
             title:'Hello World',
              user: {
                firstName:'Karan',
                lastName:'Singh'
             },
             showName:true,
             items:[
                 {title:'Item One'},
                 {title:'Item Two'},
                 {title:'Item Three'}
             ]
         }
     },
         methods:{
             greet:function(greeting) {
                 alert(greeting);
             },
         
         pressKey:function(e){
             console.log(e.target.value);
         },

         enterHit: function(){
             console.log('You hit Enter');
          }
        }
 }
</script>

<style scoped>

</style>
