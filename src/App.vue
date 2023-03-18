<template>
  <div id="app">
    <div class="container">
      <KForm @onNoteAdd="addNote" />
      <KNote @onNoteEdit="editNote" @onNoteDelete="deleteNote" class="mt-4" v-for="note in notes" :note="note" />
    </div>
  </div>
</template>

<script>
import KForm from "./components/KForm.vue"
import KNote from "./components/KNote.vue";
export default {
  name: 'App',
  components: {
    KForm,
    KNote
  },
  data() {
    return {
      notes: [
        {
          title: "aaa1",
          description: "bbb"
        }, {
          title: "aaa2",
          description: "bbb2"
        }
      ]
    }
  },
  methods: {
    addNote(note) {
      this.notes.push(note)
    },
    deleteNote() {
      console.log("delete")
    },
    editNote() {
      console.log("edit")
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
