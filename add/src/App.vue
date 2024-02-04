<template>
  <Chec 
  :dela="dela" 
  @delit="delit" 
  :newDelas="newDelas" 
  @addDela="addDela" 
  />
</template>
<script>
import Chec from './components/Chec.vue'
export default {
  name: 'App',
  components: {
    Chec
  },
  data() {
    return {
      dela: [
        { id: 1, text: 'Сделать дз' },
        { id: 2, text: 'Покушать' },
        { id: 3, text: 'Налить чай' },
        { id: 4, text: 'Погулять' }
      ],
    }
  },
  methods: {
    addDela(newDelas) {
      this.dela.unshift({
        id: Date.now(),
        text: newDelas
      })
    },

    delit(id) {
      this.dela = this.dela.filter(dela => dela.id !== id)
    }
  }
}
</script>
<style></style>
