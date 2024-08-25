<script>
export default {
  name: "cardForm",
  data() {
    return {
      tituloTarjeta: 'Visa Classic Crédito',
      Chip: '/img/chip.png',
      numeroTarjeta: '',
      fechaExpiracion: '',
      titularTarjeta: '',
      TipoTarjeta: '/img/visa.png',
    };
  }
}
</script>

<template>
  <div id="app">
    <form>
      <div>
        <label>Título de la tarjeta: </label>
        <input v-model="tituloTarjeta" />
      </div>

      <div>
        <label>Chip SRC: </label>
        <input v-model="Chip" disabled />
      </div>

      <div>
        <label>Número: </label>
        <input v-model="numeroTarjeta" maxlength="19" placeholder="XXXX XXXX XXXX XXXX" />
      </div>

      <div>
        <label>Fecha de expiración: </label>
        <input v-model="fechaExpiracion" maxlength="5" placeholder="MM/AA" />
      </div>

      <div>
        <label>Propietario: </label>
        <input v-model="titularTarjeta" placeholder="Nombre del titular" />
      </div>

      <div>
        <label>Tipo de tarjeta SRC: </label>
        <input v-model="TipoTarjeta" disabled />
      </div>
    </form>

    <div class="carnet">
      <h3>{{ tituloTarjeta }}</h3>
      <img width="40" :src="Chip" alt="Chip de la tarjeta" />
      <div>
        <h2>{{ numeroTarjeta }}</h2>
        <span>Fecha Expiración: <b>{{ fechaExpiracion }}</b></span>
      </div>
      <footer>
        <span>{{ titularTarjeta }}</span>
        <img :src="TipoTarjeta" width="60" alt="Logo de la tarjeta" />
      </footer>
    </div>
  </div>
</template>

<style scoped>
* {
  margin: 0;
}

form {
  padding: 18px;
  border-radius: 15px;
  border: ridge 1px;
  box-shadow: 2px 2px 5px gray;
  font-weight: bold;
  display: flex;
  flex-direction: column;
  gap: 15px;
  justify-content: center;
  background-color: #f5f5f5;
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
  background: linear-gradient(135deg, #b7950b, #f4d03f);
  color: #f5f5f5;
  border-radius: 15px;
  padding: 20px;
  box-shadow: 0px 0px 15px 4px rgba(0, 0, 0, 0.7);
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.carnet img[alt="Chip de la tarjeta"] {
  box-shadow: 2px 2px 8px rgba(0, 0, 0, 0.6);
  border-radius: 5px;
}

h3 {
  font-size: 22px;
  color: #ffffff;
  text-shadow: 2px 2px 4px #423c23,
    0px 0px 10px rgba(0, 0, 0, 0.5);
  text-transform: uppercase;
  margin-bottom: 10px;
  letter-spacing: 1px;
}

h2 {
  font-size: 28px;
  letter-spacing: 4px;
  margin-bottom: 15px;
  color: #fff;
  text-shadow: 0px 0px 10px rgba(0, 0, 0, 0.5);
  font-family: 'Times New Roman', Times, serif;
}

b {
  font-size: 16px;
  color: #f5c13d;
}

footer {
  display: flex;
  justify-content: space-between;
  align-items: flex-end;
  font-weight: bold;
  font-size: 18px;
  text-transform: uppercase;
  font-style: italic;
}
</style>