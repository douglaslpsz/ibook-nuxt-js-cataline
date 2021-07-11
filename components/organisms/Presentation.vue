<template>
  <div class="presentation">
    <p>
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Obcaecati, ab. Eos, officia officiis? Nulla, reiciendis illo. Obcaecati porro optio sed, alias distinctio saepe quo omnis at voluptates voluptatem, dolorum rem?
    </p>
    <img src="@/assets/img/presentation.svg" alt="Apresentação do iBook">
  </div>
</template>

<style lang="scss" scoped>
.presentation {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  grid-gap: 2rem;
  align-items: center;
  @include screen('small', 'medium') {
    grid-template-columns: 1fr;
  }
  p {
    line-height: 26px;
  }
  img {
    max-width: 100%;
  }
}
</style>