<template>
  <section class="container">
    <div class="column is-multiline">
    </div>
  </section>
</template>

<script>
  import dogApi from '@/api/dog';
  import {mapState} from 'vuex';

  export default {
    async fetch({store, params}) {
      const json = await dogApi.dogs(params.breed);
      store.commit('dog_list_update', json)
    },
    computed: mapState(['dog_list']),
  }
</script>

