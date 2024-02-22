<template>
  <v-card width="400" color="#2962FF">
    <v-card-title>Welcome</v-card-title>
    <v-card-text>
      <v-form v-model="valid">
        <v-text-field v-model="usuario" type="text" placeholder="Escribe tu Usuario" label="Usuario" :rules="[rules.required]" />
        <v-text-field v-model="password" type="password" placeholder="Escribe la contraseña" label="Contraseña" :rules:="[rules.required, rules.password]" />
      </v-form>
    </v-card-text>
    <v-card-actions>
      <v-btn block elevation="10" color="#00BFA5" @click="loginUser">
        <v-icon color="#1A237E">
          mdi-account
        </v-icon>
        Login
      </v-btn>
    </v-card-actions>
  </v-card>
</template>

<script>
export default {
  data () {
    return {
      valid: false,
      usuario: '',
      password: '',
      rules: {
        required: value => !!value || 'Required.',
        password: value => value.length > 5 || 'Contraseña requiere 6 caracteres'
      }
    }
  },
  methods: {
    loginUser () {
      console.log('Presionaste el boton')
    }
  }
}
</script>

<style scoped>
</style>
