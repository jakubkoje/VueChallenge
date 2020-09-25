<template>
  <b-container>
    <b-row>
      <b-col>
        <h1>ÚDAJE</h1>
      </b-col>
    </b-row>
    <b-row>
      <b-col>
        <div v-if="Object.keys(user).length">
          <h6
            v-for="(data, i) in user"
            :key="i"
          >
            {{ i }}: {{ data }}
          </h6>
        </div>
        <div v-else>
          <h6>Ziadne ulozene udaje</h6>
        </div>
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
import { mapState } from 'vuex';

export default {
  name: 'Information',
  computed: {
    ...mapState(['user']),
  },
};
</script>
