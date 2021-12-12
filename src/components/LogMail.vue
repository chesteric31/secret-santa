<template>
  <form @submit.prevent="submit">
    <p>
      <input id="email" v-model="email" placeholder="email" type="email"/>
    </p>
    <p>
      <input id="nom" v-model="nom" placeholder="nom"/>
    </p>
    <p>
      <button type="submit">A qui je dois faire plaisir?</button>
    </p>
  </form>
  <p v-if="matching">
    {{ matching }}
  </p>
</template>

<script>
import axios from 'axios'

export default {
  name: "LogMail",
  data() {
    return {
      email: "",
      nom: "",
      matching: ""
    }
  },
  methods: {
    submit() {
      console.log(this.email)
      let config = {
        headers: {
          //'x-apikey': '0dfb081eb2f35ad331fb5112019cd040f4c39'
          'x-apikey': '61b65bb372a03f5dae82230e'
        }
      };
      axios
          .get('https://secretsanta-f4e9.restdb.io/rest/persons?max=2', config)
          .then((response) => {
            console.log(response)
            if (response && response.data) {
              this.matching = response.data[0].matching_name + ' - ' + response.data[0].matching_email;
            }
          })
          .catch((error) => {
            console.error(error);
            alert(error);
          });
    }
  }
}

</script>

<style scoped>

</style>
