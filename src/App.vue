<template>
  <div id="app">
    <v-app>
		<myHeader msg="Server Details"/>
		<v-layout row>
    		<v-flex xs12 sm6 >
      			<server />
    		</v-flex>
			<v-flex xs12 sm6>
      			<serverDetails @send-data="msg = $event"/>
    		</v-flex>
  		</v-layout>
		<myFooter/>
  	</v-app>
  </div>
</template>

<script>
import myHeader from "./components/header.vue";
import myFooter from "./components/footer.vue";
import serverDetails from "./components/serverDetails.vue";
import server from "./components/server.vue";

export default {
  name: "app",
  components: {
    myHeader,
    myFooter,
    serverDetails,
    server
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
