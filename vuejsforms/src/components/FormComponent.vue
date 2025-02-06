<template>
  <div id="app">
    <p>Type Something...</p>
    <p>Enter Something</p>

    <form v-on:submit.prevent>
      <input type="text" v-on:keypress="submit" v-model="name">
    </form>

    <ol v-bind:style="{ listStyle: 'none' }">
      <li v-for="(item, index) in data" v-bind:key="index">
        <span v-if="editingIndex !== index">{{ item }}</span>
        <input v-else type="text" v-model="editedText" v-on:keypress.enter="saveEdit(index)" />

        <button v-if="editingIndex !== index" v-on:click="edit(index)">Edit</button>
        <button v-else v-on:click="saveEdit(index)">Save</button>
        
        <button v-on:click="deleteItem(index)">Delete</button>
      </li>
    </ol>
  </div>
</template>

<script>
export default {
  name: 'FormComponent',
  data() {
    return {
      name: "",
      data: [],
      editingIndex: null, 
      editedText: ""
    };
  },
  methods: {
    
    submit(e) {
      if (e.key === "Enter") {
        this.data.push(this.name);
        this.name = ""; 
      }
    },

    
    deleteItem(index) {
      this.data.splice(index, 1);
    },

    
    edit(index) {
      this.editingIndex = index;
      this.editedText = this.data[index];
    },

    
    saveEdit(index) {
      if (this.editedText !== "") {
        this.data[index] = this.editedText;
      }
      this.editingIndex = null; 
      this.editedText = "";
    }
  }
};
</script>

<style scoped>
button {
  margin-left: 5px;
}
</style>
