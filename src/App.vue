<script setup>
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from './components/HelloWorld.vue'
</script>

<template>
  <!-- <header>
    <img alt="Vue logo" class="logo" src="@/assets/logo.svg" width="125" height="125" />

    <div class="wrapper">
      <HelloWorld msg="You did it!" />

      <nav>
        <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/about">About</RouterLink>
      </nav>
    </div>
  </header>

  <RouterView /> -->


  <div>
    <h1>{{ name }}</h1>
    <p>{{ sid }}</p>

    <input 
      v-on:keyup.enter="addItem"
      type="text" placeholder="Add new item" name="additem" v-model="newItem"/>
    {{ newItem }}

    <br/>
    <br/>

    <button v-on:click="addItem">Submit</button>

    <br/>
    <br />

    <label>
      <input type="checkbox" v-model="isNewItemHighPriority">
      High priority
    </label>

    <br />
    
    <select v-model="newItemHighPriority">
      <option value="no">No</option>
      <option value="yes">Yes</option>
    </select>

    <br/>

    {{ isNewItemHighPriority }}

    <br />
    {{ newItemHighPriority }}


    <div>
      
      <div><label><input type="checkbox" v-model="icecreamFavor" value="vanila"/> Vanila</label> </div>
      <div><label><input type="checkbox" v-model="icecreamFavor" value="rose"/> Rose</label></div>
      <div><label><input type="checkbox" v-model="icecreamFavor" value="starbery"/> Stab</label></div>
      <div><label><input type="checkbox" v-model="icecreamFavor" value="orange"/> Orange</label></div>
    </div>



    <ul>
      <li v-for="item in items" :key="item.id">{{ item.label }}</li>
    </ul>

  </div>

</template>

<script>

export default {
  data () {
    return {
      name: "oVue from state",
      sid: "o Sid",
      newItem: "",
      isNewItemHighPriority: false,
      newItemHighPriority: "no",

      icecreamFavor: [],

      items: [
        {id: 1, label:"One"},
        {id: 2, label: "Two"},
        {id:3, label: "Three"}
      ]
    }
  },
  methods: {
    addItem() {
      this.items.push({id: this.items.length+1, label: this.newItem})
      this.newItem = ""
    }
  }


}


</script>

<style scoped>
header {
  line-height: 1.5;
  max-height: 100vh;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

nav {
  width: 100%;
  font-size: 12px;
  text-align: center;
  margin-top: 2rem;
}

nav a.router-link-exact-active {
  color: var(--color-text);
}

nav a.router-link-exact-active:hover {
  background-color: transparent;
}

nav a {
  display: inline-block;
  padding: 0 1rem;
  border-left: 1px solid var(--color-border);
}

nav a:first-of-type {
  border: 0;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  nav {
    text-align: left;
    margin-left: -1rem;
    font-size: 1rem;

    padding: 1rem 0;
    margin-top: 1rem;
  }
}
</style>
