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
import { eventBus } from "../main";
export default {
  name: "serverDetails",
  props: {
    msg: String
  },
  created() {
    eventBus.$on("send-data", data => {
      this.msg = data;
    });
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
