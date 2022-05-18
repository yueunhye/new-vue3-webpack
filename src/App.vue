<template>
  <!-- Remove & use example component! -->
  <button @click="click">
    click!
  </button>
  <ul>
    <!-- 객체구조분해할당 fruit -->
    <li
      v-for="{id, name} in newFruits"
      :key="id">
      {{ name }}-{{ id }}
    </li>
  </ul>
</template>

<script>
// import HelloWorld from '~/components/HelloWorld'
import shortid from 'shortid'

export default {
  data() {
    return {
      fruits: ['apple', 'banana', 'grape']
    }
  },
  computed: {
    newFruits() {
      return this.fruits.map( fruit => ({
        id: shortid.generate(),
        name: fruit
      }))
    }
  },
  methods: {
    click() {
      this.fruits.push('orange')
    } 
  }
}
</script>