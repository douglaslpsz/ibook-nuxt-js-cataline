<template>

  <div class="error-404">
    <div class="content-error">
      <img src="@/assets/img/404.svg" alt="Página não encontrada" />
      <h2>Página não encontrada</h2>
      <NuxtLink class="read-book" :to="`/`" >
        Página inicial
      </NuxtLink>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.error-404 {
  height: 100vh;
  background: #1b1b1b;
  display: grid;
  justify-content: center;
  align-items: center;
  img {
    width: 60%;
    justify-self: center;
  }
  h2 {
    color: #f7f7f7;
    justify-self: center;
    margin-top: 30px;
    font-size: 16px;
  }
}

.read-book {
  margin-top: 30px;
  background: #292929;
  color: #f7f7f7;
  text-transform: uppercase;
  font-weight: 700;
  width: 200px;
  height: 42px;
  font-size: 1.1rem;
  display: grid;
  justify-content: center;
  align-items: center;
  transition: all 300ms ease;
  justify-self: center;
  &:hover {
    transition: all 70ms ease;
    -webkit-box-shadow: inset 0 0 0 3px #246ec2!important;
    box-shadow: inset 0 0 0 3px #246ec2!important;
  }
  &:active {
    transition: all 70ms ease;
    opacity: 0.89;
    -webkit-box-shadow: inset 0 0 0 3px #246ec2!important;
    box-shadow: inset 0 0 0 3px #246ec2!important;
    }
}

  .content-error{
    display: grid;
    align-items: center;
    justify-content: center;
  }

</style>