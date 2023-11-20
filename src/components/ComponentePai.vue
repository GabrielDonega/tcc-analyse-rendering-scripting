<template>
  <div class="componente-pai">
    <img src="../assets/logo.svg" alt="Vue Logo" />
    <input v-model="randomName" placeholder="Nome" />
    <input v-model="randomAge" placeholder="Idade" />
    <div class="input-container" v-if="nivel >= 2">
      <componente-filho
          v-for="index in numberOfChildren"
          :key="index"
      />
    </div>
  </div>
</template>

<script>
import ComponenteFilho from "./ComponenteFilho.vue";
export default {
  data() {
    return {
      randomName: "",
      randomAge: "",
      firstNames: ["Teste 1", "Teste 2", "Teste 3", "Teste 4", "Teste 5", "Teste 6", "Teste 7", "Teste 8", "Teste 9", "Teste 10"],
      lastNames: ["Teste I", "Teste II", "Teste III", "Teste IV", "Teste V", "Teste VI", "Teste VII", "Teste VIII", "Teste IX", "Teste X"]
    }
  },
  components: {
    ComponenteFilho
  },

  props:{
    nivel: {
      default: 1
    }
  },

  created() {
    this.randomName = this.generateRandomName()
    this.randomAge = this.generateRandomAge()
  },

  computed: {
    numberOfChildren() {
      if (this.nivel === 3) {
        return 5
      }else if(this.nivel === 2){
        return 1
      }
      return 2
    }
  },

  methods: {
    generateRandomName() {
      const randomFirstName = this.firstNames[Math.floor(Math.random() * this.firstNames.length)]
      const randomLastName = this.lastNames[Math.floor(Math.random() * this.lastNames.length)]
      return `${randomFirstName} ${randomLastName}`
    },
    generateRandomAge() {
      return Math.floor(Math.random() * (65 - 18 + 1)) + 18
    }
  }
};
</script>

<style>
.componente-pai {
  display: flex;
  max-width: 300px;
  flex-direction: column;
  align-items: center;
  padding: 20px;
  border: 1px solid #ccc;
  border-radius: 5px;
}

img {
  width: 100px;
  height: 100px;
  margin-bottom: 10px;
}

.input-container {
  display: flex;
  flex-direction: column;
  align-items: center;

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
