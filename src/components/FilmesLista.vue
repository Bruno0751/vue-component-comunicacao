<template>
  <div class="row">

    <!-- coluna 1 -->
    <div class="col-8">

      <h2>Filmes</h2>

      <ul class="list-group list-group-flush">

        <FilmesListaIten
          v-for="filme in filmes"
          :key="filme.id"
          :filme="filme"
          @selecionarFilme="filmeSelecionado = $event"
        />

      </ul>
    </div>

    <!-- coluna 2 -->
    <div class="col-4">

      <FilmesListaItenInfo />

    </div>

  </div>
</template>

<script>

import FilmesListaIten from './FilmesListaIten.vue'
import FilmesListaItenInfo from './FilmesListaItenInfo.vue'

export default {
  components: {
    FilmesListaIten,
    FilmesListaItenInfo
  },
  data () {
    return {
      filmes: [
        {id: 1, titulo: 'Viuva Negra', ano: 2021},
        {id: 2, titulo: 'Homem Aranha de Volta ao Lar', ano: 2019},
        {id: 3, titulo: 'Homem de Ferro', ano: 2001},
      ],
      filmeSelecionado: undefined,
    }
  },
}
</script>
