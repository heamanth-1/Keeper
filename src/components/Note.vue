<template>
    <div class="notes">
    <div :key="note.id" v-for="note in data" className="note">
      <h1>{{ note.name }}</h1>
      <p>{{ note.message }}</p>
      <button @click="deleteNote(note.id)"><i class="fa-solid fa-trash"></i></button>
    </div>
     </div>
</template>

<script>
export default {
  name: 'note',
  props: {
    data: Array

  },
  emits: ['delete-note'],
  methods: {
    deleteNote (id) {
      this.$emit('delete-note', id)
    }
  }
}

</script>

<style scoped>
.notes{
  margin: auto;
  margin: 0 3rem 0 0;
}
.note {
  background: #fff;
  border-radius: 7px;
  box-shadow: 0 2px 5px #ccc;
  padding: 10px;
  width: 15%;
  margin: 1rem;
  float: right;
  margin-right: 5rem;
}
.note h1 {
  font-size: 1.1em;
  margin-bottom: 6px;
}
.note p {
  font-size: 1.1em;
  margin-bottom: 10px;
  white-space: pre-wrap;
  word-wrap: break-word;
}

.note button {
  position: relative;
  float: right;
  margin-right: 10px;
  color: #f5ba13;
  border: none;
  width: 36px;
  height: 36px;
  cursor: pointer;
  outline: none;
}
.fa-trash{
  color: #f5ba13;
  font-size:1.5rem;
}
.fa-trash:hover{
  transform: scale(1.1);
  aspect-ratio: 1,2;
   transition: 0.1s;
}
</style>
