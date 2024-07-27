<template>
  <div>Hello {{ title }} {{ name }}</div>
  <!-- binding texts -->
  <div v-text="country"></div>
  <br />
  <!-- binding html -->
  <div v-html="button"></div>
  <br />
  <!-- v-bind attribute(id) -->
  <h2 v-bind:id="headingAttribute">Create Account</h2>
  <!-- bind boolean attributes-->
  <button v-bind:disabled="isDisabled">Create Post</button>
  <!-- binding class attribute -->
  <p v-bind:class="hintClass">
    If you are unauthorized you can not perform this action
  </p>
  <!-- conditional class binding ternary -->
  <button v-bind:class="status ? 'available' : 'unvailable'">
    Available Status
  </button>
  <!--  -->
  <!-- Array binding(class) -->
  <h2 v-bind:class="['available', 'new']">Newly launched Available Shows</h2>
  <!-- multiple class binding in array | available movies that are live or not-->
  <h2 v-bind:class="[status && 'available', isLive ? 'live' : 'notlive']">
    Show is Airing now
  </h2>
  <!--  -->

  <!--  -->
  <!-- example of object conditional  objects(status,isLive) -->
  <h2
    v-bind:class="{
      available: status,
      notlive: !isLive,
      live: isLive,
    }">
    Show is Airing now
  </h2>
  <!--  -->
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      title: "Mr.",
      name: "Kawsar",
      country: "Bangladesh",
      button:
        '<a class="button" href="https://github.com/KawsarAhmad43/">View Profile</a>',
      //  boolean attribute
      isDisabled: true,
      // setting attribute dynamically
      headingAttribute: "heading",
      // class attribute
      hintClass: "hintMssg",
      status: true,
      isLive: false,
    };
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.button {
  padding: 10px 20px;
  background-color: rgb(8, 236, 210);
  border-radius: 10px;
  text-decoration: none;
}
/* id=heading */
#heading {
  font-family: "Trebuchet MS", "Lucida Sans Unicode", "Lucida Grande",
    "Lucida Sans", Arial, sans-serif;
  color: blue;
}
/* class */
.hintMssg {
  color: red;
}
.available {
  background-color: rgb(1, 164, 31);
  color: black;
}
.unvailable {
  background-color: rgb(210, 4, 4);
  color: white;
}

.new {
  font-weight: bolder;
  text-decoration: dashed;
}

.live {
  text-decoration: overline;
  color: aqua;
}

.notlive {
  text-decoration: line-through;
  color: red;
}
</style>
