<template>
  <img alt="logo" src="./assets/yangfei.png" width="250" height="250">
  <p>{{title}} {{visitor}}</p>
  <button @click="visitor++">Increase</button>
  <button @click="visitor--">Decrease</button>
  <br>
  <button @click="Show">
    <span v-if="!accepted">Show it!</span>
    <span v-if="accepted">Nah, no more</span>
    </button>
  <div v-if="accepted">
    <p>What's your name ?</p>
    <input type="text" name="name" v-model="change">
    <button @click="ChangeName(change)">Submit</button>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    // HelloWorld,
  },
  methods: {
    ChangeName(me){
      try {
        if(me=="") throw "empty";
        else {
          this.title=me
        }
      }
      catch(err) {
        alert("Input is " + err);
      }
    },
    Show(){
      this.accepted = !this.accepted
    }
  },
  data() {
    return {
      accepted: false,
      title: 'Visitor',
      change: '',
      visitor: 1
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
</style>
