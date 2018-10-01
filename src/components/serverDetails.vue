<template>
  <v-layout row>
    	<v-flex xs9>
			<h2>Server Status</h2>
			<p>{{msg}}</p>
    	</v-flex>
	<v-flex xs3></v-flex>
  </v-layout>
</template>

<script>
export default {
  name: 'serverDetails',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
