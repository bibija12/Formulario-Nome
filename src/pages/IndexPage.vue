<template>
  <q-page class="container" padding>
    <p class="text-h4">Formulario</p>
      <q-form
      @submit="submitForm"
      class="row q-col-gutter-md"
      ref="myform"
      >
      <q-input
        rounded outlined
        clearable
        clear-icon="close"
        v-model="form.nome"
        color="green"
       label="Nome"
      class="çol-md-12 col-sm-12 col-xs-12"
      :rules="[
        val => val && val.length > 0 || 'Nome obrigatorio'
      ]"
      >
      <template v-slot:prepend>
        <q-icon name="person" />
      </template>
      </q-input>

       <q-input
        v-model="form.email"
        type="email"
        label="Email"
        suffix="@gmail.com"
        rounded outlined
       class="çol-md-12 col-sm-12 col-xs-12"
       :rules="[
        val => val && val.length > 0 || 'Email obrigatorio'
      ]"

      >
      <template v-slot:prepend>
        <q-icon name="mails" />
      </template>
      </q-input>

      <q-input
        v-model="form.telefone"
        label="Telefone"
        rounded outlined
       class="çol-md-12 col-sm-12 col-xs-12"
       mask="(###) ## ### ####"
       unmasked-value
       :rules="[
        val => val && val.length > 0 || 'Telefone obrigatorio',
        val => val.length === 12 || 'coloque um numero válido'
      ]"
      />
      <div class="col-12">

        <q-btn
         label="confirmar"
          type="submit"
           color="primary"
           class="float-right"
           />

      </div>
      </q-form>
  </q-page>
</template>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'Indexpage',
  data () {
    return {
      form: {
        nome: '',
        email: '',
        telefone: ''
      }
    }
  },
 methods: {
    submitForm() {
      alert('É um prazer te conhecer: ' + this.form.nome);
    }
  }
})
</script>

