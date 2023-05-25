<template>
  <div id="app">
    <Logo />
    <div>
      <router-view/>
    </div>
  </div>
</template>
<script>
import Logo from '@/components/Logo.vue';

export default {
  components: {
    Logo,
  },
}
</script>
<style lang="scss">
@import '@/styles/main.scss';
html {
  background: $off;
  margin: 0;
}
body {
  margin: 0;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: $text;
  letter-spacing: 0;
  font-family: "Raleway", sans-serif;
  max-width: 100vw;
  margin: 0 auto;
}
p,
table,
ul,
ol,
li {
  font-family: "Lato", sans-serif;
  color: $text;
}
h1 {
  font-weight: 900;
  font-size: 4rem;
  margin-bottom: 20px;
  // letter-spacing: 2px;
  line-height: 3.5rem;
}
h2 {
  font-weight: 500;
  font-size: 1.5rem;
  text-transform: uppercase;
  letter-spacing: 10px;
}
h3 {
  font-size: 1.35rem;
  line-height: 1.75rem;
  font-weight: 600;
  margin-top: 40px;
}
h4 {
  font-size: 1.2rem;
  font-weight: 500;
  line-height: 1.5;
  letter-spacing: 3px;
  text-transform: uppercase;
  margin-bottom: 10px;
}
h5 {
  font-size: 1.1rem;
  font-weight: 400;
  margin-bottom: 10px;
}
h6 {
  font-size: 0.75rem;
  font-weight: 500;
  letter-spacing: 4px;
  text-transform: uppercase;
  margin-bottom: 10px;
}
p {
  margin: 0 0 25px;
  font-weight: 500;
  font-size: 1rem;
  line-height: 1.5rem;
  color: $text;
  max-width: 600px;
}
a {
  border: none;
  font-weight: 600;
  letter-spacing: 0.25px;
  font-family: "Lato", sans-serif;
  text-decoration: none;
  color: $heavy-op;
}
input,
label,
textarea {
  font-family: "Lato", sans-serif;
}
ul,
ol {
  padding: 5px 0 10px 20px;
  font-weight: 400;
  line-height: 1.25rem;
}
li {
  padding-bottom: 15px;
}
.page {
  display: flex;
  flex-direction: column;
  align-content: center;
  margin-left: 60px;
}
@import '@/styles/media.scss';
</style>
