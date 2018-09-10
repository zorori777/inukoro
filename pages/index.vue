<template>
  <div></div>
</template>

  <script>
    import dogApi from '@/api/dog'

    export default {
        async fetch({store}) {
          let json = await dogApi.breeds();
          store.commit('breed_list_update', json)
        },
    }
  </script>
