<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <VForm @submit="onSubmit" v-slot="{ errors }">
      {{ errors }}
      <div class="mb-3">
        <label for="email" class="form-label">Email</label>
        <VField id="email" class="form-control" name="email" type="email" placeholder="請輸入 Email" rules="email|required" :class="{'is-invalid':errors['email']}" v-model="user.email"></VField>
        <ErrorMessage class="invalid-feedback" name="email"></ErrorMessage>
      </div>
      <button class="btn btn-primary" type="submit">送出</button>
    </VForm>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'HomeView',
  components: {
    HelloWorld
  },
  data () {
    return {
      user: {
        email: ''
      }
    }
  },
  methods: {
    onSubmit (value) {
      console.log(value)
    }
  },
  created () {

  }
}
</script>
