<template>
	<v-layout row>
			<v-flex xs9>
				<h2>Server Status</h2>
				<h3><strong>Name:</strong> {{msg.Type}}</h3>
				<h3><strong>IP:</strong> {{msg.IP}}</h3>
				<h3><strong>Time Alive:</strong> {{msg.TimeAlive}}</h3>
				<h3><strong>Status:</strong> {{msg.Stat}}</h3>
			</v-flex>
	<v-flex xs3></v-flex>
	</v-layout>
</template>

<script>
import { eventBus } from "../main";
export default {
  name: "serverDetails",
  props: {
    msg: Object
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
p {
  padding-top: 30px;
  font-size: 30px;
}
</style>
