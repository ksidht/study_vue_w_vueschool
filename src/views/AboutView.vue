<template>
  <div class="about">
    <h1>This is an about page</h1>

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
<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
