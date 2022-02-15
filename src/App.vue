<template>
<Header/>
<AddNote @add-note="addNote"/>
<Note @delete-note="deleteNote" :data= "data"/>
</template>

<script>
import Note from './components/Note'
import Header from './components/Header'
import AddNote from './components/AddNote'
export default {
  name: 'App',
  components: {
    Header,
    AddNote,
    Note
  },
  data () {
    return {
      data: []
    }
  },
  methods: {
    deleteNote (id) {
      this.data = this.data.filter((data) => data.id !== id)
    },
    addNote (note) {
      note.id = Number(this.data.length) + 1
      console.log(note)
      this.data.push(note)
      //
    }
  },
  created () {
    this.data = [
      { id: 1, name: 'virat', message: 'be the best you can be ' },
      { id: 2, name: 'rohit', message: 'sun will rise again tommorrow' },
      { id: 3, name: 'Dhoni', message: "i don't see any in em" },
      { id: 4, name: 'kane Williamson', message: 'its me who should decide , whether i smile or cry . i prefer smile ' },
      { id: 5, name: 'Afridi', message: ' Age is just a number' },
      { id: 6, name: 'de villiers', message: ' ipl is harder than world cup' }

    ]
  }
}
</script>

<style>
*{
  padding: 0;
  margin: 0;
}
body {
  background: #eee;
}
</style>
