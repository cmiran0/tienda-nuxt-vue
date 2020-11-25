<template>
  <div>
    <ul>
      <li v-for="item in items" :key="item.id">
        {{ item.name }} {{ item.pvp }}
        <button v-on:click="addTicket(item)">+</button>
        <button v-on:click="delTicket(item)">-</button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "lista-productos",

  props: ['items'],
  data: function () {
    return {
      id: 2,
      name: null,
      pvp: null,
    }
  },
  methods: {
    addTicket(item) {
      this.$emit('subir-producto-ticket', item)
    },
    delTicket(item) {
      this.$emit('borrar-producto-ticket', item)
    }
  }
}
</script>

<style scoped>

</style>
