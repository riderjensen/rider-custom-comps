<template>
	<v-layout row>
		<v-flex xs3></v-flex>
		<v-flex xs9>
				<v-list two-line>
					<template v-for="(item, i) in list">
						<v-list-tile
							:key="item.Name"
							@click="emitMeCaptain(item.Status, i)"
						>
							<v-list-tile-content v-bind:class="{ active: item.active }">
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
        {
          Name: "Server One",
          Status: {
            Type: "Media Server",
            IP: 1001,
            TimeAlive: "10/18/19",
            Stat: "Good"
          },
          active: false
        },
        {
          Name: "Server Two",
          Status: {
            Type: "Hosting Server",
            IP: 1001001,
            TimeAlive: "4/6/11",
            Stat: "Bad"
          },
          active: false
        },
        {
          Name: "Server Three",
          Status: {
            Type: "Serving Server",
            IP: 1023947234,
            TimeAlive: "5/12/78",
            Stat: "On Fire"
          },
          active: false
        },
        {
          Name: "Server Four",
          Status: {
            Type: "Backup Server",
            IP: 112312451,
            TimeAlive: "1/19/16",
            Stat: "Flooded"
          },
          active: false
        },
        {
          Name: "Server Five",
          Status: {
            Type: "Load Balancing Server",
            IP: 23462546,
            TimeAlive: "7/18/19",
            Stat: "Bees are nesting"
          },
          active: false
        }
      ]
    };
  },
  methods: {
    emitMeCaptain(status, i) {
      this.list.forEach(element => {
        element.active = false;
      });
      this.list[i].active = !this.list[i].active;
      eventBus.$emit("send-data", status);
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
* {
  text-align: center;
}
.active {
  background-color: tomato;
  color: #fff;
}
</style>
