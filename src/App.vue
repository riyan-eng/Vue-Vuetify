<template>
  <v-app>
    <v-main>
      <Form/>
    </v-main>
  </v-app>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Form from './components/Form.vue'

export default {
  name: 'App',

  components: {
    HelloWorld,
    Form
  },

  data: () => ({
    //
  }),
}
</script>
