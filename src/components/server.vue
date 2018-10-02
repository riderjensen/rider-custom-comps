<template>
  <v-layout row>
	  <v-flex xs3></v-flex>
    <v-flex xs9>
        <v-list two-line>
          <template v-for="item in list">
            <v-list-tile
              :key="item"
              @click="eventBus.$emit('send-data', item.Status)"
            >
              <v-list-tile-content>
                <v-list-tile-title v-html="item.Name"></v-list-tile-title>
              </v-list-tile-content>
            </v-list-tile>
          </template>
        </v-list>
    </v-flex>
  </v-layout>
</template>

<script>
import { eventBus } from "../main";
export default {
  name: "server",
  props: {
    msg: String
  },
  data: () => {
    return {
      list: [
        { Name: "Server One", Status: "Good" },
        { Name: "Server Two", Status: "Bad" },
        { Name: "Server Three", Status: "On Fire" },
        { Name: "Server Four", Status: "Flooded" },
        { Name: "Server Five", Status: "Beehive" }
      ]
    };
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
* {
  text-align: center;
}
</style>
