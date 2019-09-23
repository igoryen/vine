<template>
  <div class="about">
    <h1>About</h1>
    <p>This is the TodoList app v1.0.0. It is part of the Vue crash course on Youtube.</p>
    <div id="pickle">
      <input type="text" v-on:input="changePhrase"> 
      <p>{{something}}</p>
      <div>
          <h1>{{ sayHello() }}</h1>
      </div>
    </div>
  </div>
</template>

<script>
export default {
    name: 'Pickle',
    data(){
        return {
            something: "'Tis I, a pickle!"
        }        
    },
    methods: {
        changePhrase: function( event ){
            this.something = event.target.value;
        },
        sayHello: function(){
            return "Hello!";
        }
        
    }
}
</script>
