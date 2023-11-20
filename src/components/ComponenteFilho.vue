<template>
  <div class="componente-filho">
      <input v-model="randomData1" placeholder="Dado 1" />
      <input v-model="randomData2" placeholder="Dado 2" />
      <input v-model="randomData3" placeholder="Dado 3" />
      <input v-model="randomData4" placeholder="Dado 4" />
      <input v-model="randomData5" placeholder="Dado 5" />
  </div>
</template>

<script>
export default {
  data() {
    return {
      randomData1: "",
      randomData2: "",
      randomData3: "",
      randomData4: "",
      randomData5: "",
    }
  },

  created() {
    this.randomData1 = this.generateRandomData()
    this.randomData2 = this.generateRandomData()
    this.randomData3 = this.generateRandomData()
    this.randomData4 = this.generateRandomData()
    this.randomData5 = this.generateRandomData()
  },
  methods: {
    generateRandomData() {
      return Math.floor(Math.random() * 100)
    }
  }
}
</script>

<style scoped>
.componente-filho {
  display: flex;
  max-width: 300px;
  flex-direction: column;
  align-items: center;
  padding: 2px;
  border: 1px solid #ccc;
  border-radius: 5px;
}

img {
  width: 100px;
  height: 100px;
  margin-bottom: 10px;
}

input {
  width: 200px;
  height: 30px;
  margin: 5px;
  text-align: center;
  border: 1px solid #ccc;
  border-radius: 5px;
}

</style>
