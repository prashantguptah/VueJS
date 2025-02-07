<template>
    <div id="app">
        <FormComponent 
            v-bind:edit-index="editIndex" 
            v-bind:name="name" 
            v-on:edit-item="saveEdit"
            v-on:submit-item="submit" 
        />

        <ul class="list">
            <li v-for="(item, index) in data" :key="index" >
                <span v-if="editIndex !== index">{{ item }}</span>
                <input v-else v-model="name" />

                <button v-if="editIndex !== index" v-on:click="editItem(index)">Edit</button>
                <button v-else v-on:click="saveEdit(index)">Save</button>

                <button v-on:click="deleteItem(index)">Delete</button>
            </li>
        </ul>
    </div>
</template>

<script>
import FormComponent from "./FormComponent.vue";

export default {
    name: "ListComponent",
    components: {
        FormComponent,
    },
    data() {
        return {
            data: [],
            name: "",
            editIndex: -1
        };
    },
    methods: {
        submit(name) {
            this.data.push(name);
            this.name = "";
        },

        editItem(index) {
            console.log("Editing item at index:", index);
            this.editIndex = index;
            this.name = this.data[index];
        },

        saveEdit(index) {
            if (this.name.trim() !== "") {
                this.data[index] = this.name;
                this.editIndex = -1;
                this.name = "";
            }
        },

        deleteItem(index) {
            this.data.splice(index, 1);
        }
    }
};
</script>

<style scoped>
  
  #app{
    display: flex;
    flex-direction: column;
  }

  .list {
    margin-top: 20px;
  }
  .list li{
    display: flex;
    justify-content: center;
    gap: 20px;
  }

</style>
