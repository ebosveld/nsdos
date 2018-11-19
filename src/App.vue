<template>
  <div id="app">
    <header>NS Reisplanner</header>

	<footer>
		<ul>
			<li>
				<span>F9</span> Zoek met vertrektijd
			</li>
			<li>
				<span>F10</span> Zoek met aankomsttijd
			</li>
			<li>
				<span>?</span> Help
			</li>
		</ul>
	</footer>
  </div>
</template>

<script>
//import HelloWorld from "./components/HelloWorld.vue";

export default {
  name: "app"
  /*components: {
    HelloWorld
  }*/
};
</script>

<style lang="scss">
body {
  font-family: $font-family;
  font-size: 1.51vw;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  background: $background;
  color: $foreground;
  margin: 0;
  padding: 0;
}

header,
footer {
  width: 100%;
  background: $menu-background;
  color: $menu-foreground;
  padding: 0.175em 0.375em;
}

header {
  margin: 0;
}

footer {
  position: fixed;
  bottom: 0;

  ul,
  li {
    padding: 0;
    display: inline;
  }

  li {
    list-style-type: none;
    span {
      color: $menu-fnkey;
    }
    padding-right: 1em;
  }
}
</style>
