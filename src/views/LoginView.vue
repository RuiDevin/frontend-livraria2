<template>
  <div class="main">
    <div class="outer">
      <div class="login">
        <h2 id="login">Seja Bem-Vindo</h2>
      </div>
      <div class="form">
        <label for="input-email">email</label>
        <input id="input-email" placeholder="Insira seu email..." type="text" />
        <label for="input-senha">senha</label>
        <input
          id="input-senha"
          placeholder="Insira sua senha..."
          type="password"
        />
        <button>entre</button>
      </div>
    </div>
  </div>
</template>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap");
.main {
  height: 800px;
  display: flex;
  align-items: center;
  justify-content: center;
}
button {
  margin-left: 1%;
  width: 50%;
  height: 40px;
  border: 1px solid white;
  border-radius: 50px;
  background-color: white;
  color: #ff4d00;
  font-weight: bold;
  cursor: pointer;
}

button:hover {
  background: linear-gradient(#c26f17, #ff4d00);
  color: #fff;
}

::placeholder {
  color: #fff;
}

textarea:focus,
input:focus {
  box-shadow: 0 0 0 0;
  outline: 0;
}

label {
  font-size: 25px;
  color: white;
}
.outer {
  display: flex;
  flex-direction: row;
}
#login {
  font-size: 45px;
}
.form {
  height: 500px;
  width: 400px;
  display: flex;
  background: linear-gradient(#c26f17, #ff4d00);
  border-radius: 30px;
  white-space: nowrap;
  align-items: flex-start;
  justify-content: center;
  padding: 0 40px 0 40px;
  flex-direction: column;
}
button {
  margin: 10% auto;
}
.form input {
  justify-content: center;
  margin-bottom: 12px;
  border-bottom: 2px solid #ffffff;
  border-top: 0;
  border-right: 0;
  color: white;
  border-left: 0;
  background: transparent;
  height: 33px;
  align-items: center;
  width: 100%;
}
.login {
  color: #fca311;
  display: flex;
  margin-right: 150px;
  align-items: center;
  justify-content: center;
}
</style>
