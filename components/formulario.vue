<template>
  <div>
    <input v-model="name" type="text">
    <input v-model="pvp" type="text">
    <button v-on:click="addItem">add</button>
  </div>
</template>

<script>
export default {
  name: "formulario",
  data() {
    return {
      id: 0,
      name: null,
      pvp: null,
    }
  },
  methods: {
    addItem: function () {
      let item = {}
      item.name = this.name
      item.pvp = this.pvp
      item.id = ++this.id + 'pr'
      this.$emit('subir-producto', item)
      this.name = null
      this.pvp = null
    }

  }

}


</script>

<style scoped>

</style>
