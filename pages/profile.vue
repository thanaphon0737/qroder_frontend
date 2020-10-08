<template>
  <v-layout>
    <v-container>
      <v-row>
        <v-col cols="3">
          <v-card>
            <v-card-title>
              Profile
              <div>{{ $auth.user.email }}</div>
              <v-select v-model="role" :items="items" label="Role"></v-select>
              <v-btn @click="savedata">SAVE</v-btn>
              {{role}}
            </v-card-title>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </v-layout>
</template>
<script>
import axios from 'axios'
export default {
  middleware: 'auth',
  methods: {
      async savedata(){
          const response = await axios.post('api',{
              email: this.$auth.user.email,
              role: role
          })
      }
  },
  data() {
    return {
        role: '',
      items: ['Manager', 'Cheif', 'Waiter', 'Cashier'],
    }
  },
}
</script>
