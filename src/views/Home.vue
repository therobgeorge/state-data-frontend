<template>
  <div class="Home">
    <p>{{ states }}</p>
    <div id="dataMap"></div>
  </div>
</template>

//
<script>
import Datamap from "datamaps";
import axios from "axios";
export default {
  data() {
    return {
      states: [],
    };
  },
  created() {
    axios.get("/states").then((response) => {
      console.log("states", response.data);
    });
  },
  mounted() {
    new Datamap({
      scope: "usa",
      element: document.getElementById("dataMap"),
      geographyConfig: {
        highlightBorderColor: "#bada55",
        popupTemplate: function (geography, data) {
          return '<div class="hoverinfo">' + geography.properties.name + " " + "Test:" + data.test + " ";
        },
        highlightBorderWidth: 3,
      },

      fills: {
        Republican: "#CC4731",
        Democrat: "#306596",
        "Heavy Democrat": "#667FAF",
        "Light Democrat": "#A9C0DE",
        "Heavy Republican": "#CA5E5B",
        "Light Republican": "#EAA9A8",
        defaultFill: "#EDDC4E",
      },
      data: {
        AZ: {
          fillKey: "Republican",
          test: 5,
        },
        CO: {
          fillKey: "Light Democrat",
          test: 5,
        },
        DE: {
          fillKey: "Democrat",
          test: 32,
        },
        FL: {
          fillKey: "UNDECIDED",
          test: 29,
        },
        GA: {
          fillKey: "Republican",
          test: 32,
        },
        HI: {
          fillKey: "Democrat",
          test: 32,
        },
        ID: {
          fillKey: "Republican",
          test: 32,
        },
        IL: {
          fillKey: "Democrat",
          test: 32,
        },
        IN: {
          fillKey: "Republican",
          test: 11,
        },
        IA: {
          fillKey: "Light Democrat",
          test: 11,
        },
        KS: {
          fillKey: "Republican",
          test: 32,
        },
        KY: {
          fillKey: "Republican",
          test: 32,
        },
        LA: {
          fillKey: "Republican",
          test: 32,
        },
        MD: {
          fillKey: "Democrat",
          test: 32,
        },
        ME: {
          fillKey: "Democrat",
          test: 32,
        },
        MA: {
          fillKey: "Democrat",
          test: 32,
        },
        MN: {
          fillKey: "Democrat",
          test: 32,
        },
        MI: {
          fillKey: "Democrat",
          test: 32,
        },
        MS: {
          fillKey: "Republican",
          test: 32,
        },
        MO: {
          fillKey: "Republican",
          test: 13,
        },
        MT: {
          fillKey: "Republican",
          test: 32,
        },
        NC: {
          fillKey: "Light Republican",
          test: 32,
        },
        NE: {
          fillKey: "Republican",
          test: 32,
        },
        NV: {
          fillKey: "Heavy Democrat",
          test: 32,
        },
        NH: {
          fillKey: "Light Democrat",
          test: 32,
        },
        NJ: {
          fillKey: "Democrat",
          test: 32,
        },
        NY: {
          fillKey: "Democrat",
          test: 32,
        },
        ND: {
          fillKey: "Republican",
          test: 32,
        },
        NM: {
          fillKey: "Democrat",
          test: 32,
        },
        OH: {
          fillKey: "UNDECIDED",
          test: 32,
        },
        OK: {
          fillKey: "Republican",
          test: 32,
        },
        OR: {
          fillKey: "Democrat",
          test: 32,
        },
        PA: {
          fillKey: "Democrat",
          test: 32,
        },
        RI: {
          fillKey: "Democrat",
          test: 32,
        },
        SC: {
          fillKey: "Republican",
          test: 32,
        },
        SD: {
          fillKey: "Republican",
          test: 32,
        },
        TN: {
          fillKey: "Republican",
          test: 32,
        },
        TX: {
          fillKey: "Republican",
          test: 32,
        },
        UT: {
          fillKey: "Republican",
          test: 32,
        },
        WI: {
          fillKey: "Democrat",
          test: 32,
        },
        VA: {
          fillKey: "Light Democrat",
          test: 32,
        },
        VT: {
          fillKey: "Democrat",
          test: 32,
        },
        WA: {
          fillKey: "Democrat",
          test: 32,
        },
        WV: {
          fillKey: "Republican",
          test: 32,
        },
        WY: {
          fillKey: "Republican",
          test: 32,
        },
        CA: {
          fillKey: "Democrat",
          test: 32,
        },
        CT: {
          fillKey: "Democrat",
          test: 32,
        },
        AK: {
          fillKey: "Republican",
          test: 32,
        },
        AR: {
          fillKey: "Republican",
          test: 32,
        },
        AL: {
          fillKey: "Republican",
          test: 32,
        },
      },
    });
  },
};
</script>

<style>
#dataMap {
  height: 800px;
}
</style>
