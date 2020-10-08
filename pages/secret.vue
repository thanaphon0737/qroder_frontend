<template>
  <v-layout>
    <v-container>
      <v-row>
        <v-col>
          <v-card>
            <v-card-title>
              Secret
            </v-card-title>
          </v-card>

          
        </v-col>
      </v-row>
    </v-container>
  </v-layout>
</template>
<script>
export default {
    middleware: 'auth',
    layout: 'managetLay'
}
</script>