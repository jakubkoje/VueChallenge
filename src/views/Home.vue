<template>
  <b-container>
    <b-row>
      <b-col>
        <h1 class="mb-4">
          FORMULÁR
        </h1>
      </b-col>
    </b-row>
    <b-row>
      <b-col>
        <b-form @submit.prevent="submitForm()">
          <b-form-group
            id="input-group-1"
            label="Email address:"
            label-for="input-1"
            description="We'll never share your email with anyone else."
          >
            <b-form-input
              id="input-1"
              v-model="user.email"
              type="email"
              required
              placeholder="Enter email"
            />
          </b-form-group>

          <b-form-group
            id="input-group-2"
            label="Your Name:"
            label-for="input-2"
          >
            <b-form-input
              id="input-2"
              v-model="user.name"
              required
              placeholder="Enter name"
            />
          </b-form-group>

          <b-button
            type="submit"
            variant="primary"
          >
            Submit
          </b-button>
        </b-form>
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
// @ is an alias to /src

export default {
  name: 'Home',
  data() {
    return {
      user: {
        email: '',
        name: '',
      },
    };
  },
  methods: {
    submitForm() {
      this.$store.commit('setUserData', this.user);
    },
  },
};
</script>
