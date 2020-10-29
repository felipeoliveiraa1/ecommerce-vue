<template>
  <div class="login col-md-12 mb-12 col-md-4">
    <div class="box">
      <h1>Bem-Vindo(a)</h1>
      <input type="text" placeholder="Email" v-model="email" />
      <br />
      <input type="password" placeholder="Senha" v-model="senha" />
      <br />
      <div class="btn-login">
        <button @click="login">Entrar</button>
      </div>
      <p>
        Você não tem conta?
        <span>
          <router-link to="/registrar">crie uma conta</router-link>
        </span>
      </p>
      <LoginFacebook />
    </div>
  </div>
</template>

<script>
import LoginFacebook from './LoginFacebook'
export default { 
    name: 'Login',
    components: { LoginFacebook }

    }
</script>

<style scoped>
.login {
  width: 100vw;
  height: 100vh;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  text-align: center;
}
input {
  margin: 10px 0;
  width: 20%;
  padding: 15px;
  border: 1px solid black;
}

@media(max-width: 800px){
    input{
        width: 80%;
        padding: 5px;
        font-size: 20px;
        color: black;
    }
}
button {
  font-family: "Roboto", sans-serif;
  text-transform: uppercase;
  outline: 0;
  background: white;
  border: 1px solid black;
  padding: 12px;
  color: black;
  width: 10em;
  font-size: 14px;
  -webkit-transition: all 0.3 ease;
  transition: all 0.3 ease;
  cursor: pointer;
}

button:hover {
    transition-duration: 120ms;
    border: 1px solid rgba(0, 0, 0, 0.2);
    box-shadow: 0 1px 5px rgba(0, 0, 0, 0.15);
    background-color: rgba(0, 0, 0, 0.15);
}
p {
  margin-top: 40px;
  font-size: 13px;
}
p a {
  text-decoration: underline;
  cursor: pointer;
}
</style>