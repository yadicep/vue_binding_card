<script>
export default {
  name: 'App',
  data() {
    return {
      cardTitle: "Visa Classic Crédito",
      chipSrc: "",
      cardNumber: "400 580 600 700",
      expirationDate: "01/30",
      owner: "WILLIAM HENRY GATES III",
      visaSrc: "",
      imgChip: "", 
      imgVisa: "",  
    };
  },
  watch: {
    chipSrc(newVal) {
      this.imgChip = new URL(`./assets/img/${newVal}`, import.meta.url).href;
    },
    visaSrc(newVal) {
      this.imgVisa = new URL(`./assets/img/${newVal}`, import.meta.url).href;
    }
  },
}
</script>

<template>
  <div id="app">
    <form>
      <div><label>Título de la tarjeta: </label><input v-model="cardTitle"/></div>
      <div><label>Chip SRC: </label><input v-model="chipSrc"/></div>
      <div><label>Número: </label><input v-model="cardNumber"/></div>
      <div><label>Fecha de expiración: </label><input v-model="expirationDate"/></div>
      <div><label>Propietario: </label><input v-model="owner"/></div>
      <div><label>Tipo de tarjeta SRC: </label><input v-model="visaSrc"/></div>
    </form>
    <div class="carnet">
      <h3>{{ cardTitle }}</h3>
      <img :src="imgChip" width="40" alt="chip" />
      <div class="date">
        <h2>{{ cardNumber }}</h2>
        <span>Fecha Exp: <b>{{ expirationDate }}</b></span>
      </div>
      <footer>
        <span>{{ owner }}</span>
        <img :src="imgVisa" width="65" alt="visa" />
      </footer>
    </div>
  </div>
</template>

<style scoped>
  form {
    padding: 18px;
    border-radius: 20px;
    border: ridge 1px;
    box-shadow: 1px 1px 1px 1px gray;
    font-weight: bold;
    display: flex;
    flex-direction: column;
    gap: 15px;
    justify-content: center;
  }

  form div {
    display: grid;
    grid-template-columns: 100px 200px;
    align-items: center;
    gap: 5px;
  }

  form div label {
    text-align: right;
  }

  .carnet {
    width: 400px;
    height: 230px;
    background: #1c1a1e;
    color: white;
    border-radius: 20px;
    padding: 20px;
    box-shadow: 0px 0px 10px 2px black;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
  }

  h3 {
    font-size: 20px;
    text-align: start;
    letter-spacing: 0.05em;
  }

  h2 {
    font-size: 30px;
    letter-spacing: 10px;
    margin-bottom: 15px;
    text-shadow: 0px 0px 1px gold;
    font-family: Times;
    text-align: start;
  }

  .date{
    text-align: start;
  }

  b {
    font-size: 16px;
  }

  footer {
    display: flex;
    justify-content: space-between;
    align-items: flex-end;
    font-weight: bold;
    font-size: 18px;
    text-transform: uppercase;
    font-style: italic;
    letter-spacing: 0.03em;
  }
</style>
