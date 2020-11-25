<template>
  <div>
    <ul>
      <li v-for="item in ticket">
        {{ item.name }} {{ item.pvp }}
      </li>
    </ul>
    <div>TOTAL: {{ total }}</div>
  </div>
</template>

<script>
export default {
  name: "lista-ticket",
  props: ['ticket'],
  computed: {
    total() {
      let total = 0
      this.ticket.forEach((item) => {
        total += parseInt(item.pvp)
      })
      return total
    }
  }
}
</script>

<style scoped>

</style>
