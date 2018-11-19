<template>
	<div class="stations box">
		<div class="title">[ Stations ]</div>
		<ul>
			<li v-for="(station, index) in filteredStations" v-bind:class="{'selected': selected === index }" :key="station.code">
				{{ station.namen.lang }}
			</li>
		</ul>
	</div>
</template>
<script>
import axios from "axios";
export default {
  name: "StationList",
  data: function() {
    return {
      stations: [],
      selected: 0
    };
  },
  computed: {
    filteredStations: function() {
      return this.stations.filter(function(station) {
        return station.land === "NL";
      });
    }
  },
  methods: {
    fetchStations: function() {
      axios
        .get("https://ns-api.nl/reisinfo/api/v2/stations", {
          headers: {
            "x-api-key": "XIhEi0Q5H93pPKBdLb1uo4yVmGQaJ3L6c8oEBkB9"
          }
        })
        .then(response => (this.stations = response.data.payload))
        // eslint-disable-next-line
        .catch(error => console.log(error));
    }
  },
  mounted: function() {
    this.fetchStations();
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
div.stations {
  width: 28%;
  ul {
    height: 75vh;
    overflow: hidden;

    li {
      list-style-type: none;
      &.selected {
        color: white;
        &:before {
          content: "-> ";
          margin-left: -35px;
        }
      }
    }
  }
}
</style>