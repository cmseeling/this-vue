<template>
  <div>
    <h2>Vue Component</h2>
    <button @click="reset">Reset</button>
    <br/>
    <br/>
    <button @click="unbound">Unbound function</button>
    <button @click="arrow">Arrow function</button>
    <p>Object properties: {{properties}}</p>
  </div>
</template>

<script>
import _ from 'lodash';

export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data() {
    return {
      properties: "click a button to examine the 'this' object"
    }
  },
  methods: {
    unbound() {
      if (this) {
        this.properties = _.join(_.keys(this), ', ');
      } else {
        this.properties = "'this' is undefined";
      }
    },
    arrow: () => {
      if (this) {
        this.properties = _.join(_.keys(this), ', ');
      } else {
        this.properties = "'this' is undefined";
      }
    },
    reset() {
      this.properties = "click a button to examine the 'this' object"
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
