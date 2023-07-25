<script setup>
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from './components/HelloWorld.vue'
import Counter from "@/components/Counter.vue";
import  BlogPost from "@/components/BlogPost.vue";
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


  <div class="flex flex-col items-center ">

    <Counter />


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



    <div :style="{ fontSize: fontSizeRef + 'em'}">
      <BlogPost 
        v-for="item in items" 
        :key="item.id" 
        :post="item" 
        @enlarge-text="fontSizeRef += 0.1"
      >THis is SLot descriotioiotnbo</BlogPost>
    </div>

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

      fontSizeRef: 1,

      icecreamFavor: [],

      items: [
        {id: 1, title:"One" , description: "For One Id"},
        {id: 2, title: "Two", description: "For Two Id"},
        {id: 3, title: "Three", description: "For Three Id"}
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
