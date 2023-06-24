<template>
  <v-app>
    <v-main>
      <mainpage/>
    </v-main>
  </v-app>
</template>

<script>
import mainpage from './components/mainpage.vue'

export default {
  name: 'App',

  components: {
    mainpage,
  },

  data: () => ({
    //
  }),
}
</script>
