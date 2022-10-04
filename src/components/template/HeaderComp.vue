<template>
  <header>
    <div>
      <span> <RouterLink to="/editoras">Editoras</RouterLink> </span>
      <span>|</span>
      <span> <RouterLink to="/categorias">Categorias</RouterLink> </span>
      <span>|</span>
      <span> <RouterLink to="/autores">Autores</RouterLink> </span>
      <span>|</span>
      <span> <RouterLink to="/livros">Livros</RouterLink> </span>
    </div>
    <div>
      <span> <RouterLink to="/login">Login</RouterLink> </span>
    </div>
  </header>
</template>

<style>
header span {
  padding: 0 20px;
}

header {
  background: linear-gradient(#c26f17, #ff4d00);
  height: 15%;
  font-size: 1.5rem;
  padding-left: 2rem;
  color: #ffffff;
  display: flex;
  align-items: center;
  justify-content: space-between;
}

span:hover {
  color: #005eff;
}
</style>
