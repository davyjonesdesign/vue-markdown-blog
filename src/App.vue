<template>
  <div id="app">
    <Logo />
    <div>
      <router-view/>
    </div>
    <Footer />
  </div>
</template>
<script>
import Logo from '@/components/Logo.vue';
import Footer from '@/components/Footer.vue';

export default {
  components: {
    Logo,
    Footer,
  },
}
</script>
<style lang="scss">
@import '@/styles/main.scss';
html {
  margin: 0;
  background: $blue-dark-3;
}
body {
  margin: 0;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  letter-spacing: 0;
  font-family: "Raleway", sans-serif;
  max-width: 100vw;
  color: $text-light;
  margin: 0 auto;
}
p,
table,
ul,
ol,
li {
  font-family: "Lato", sans-serif;
}
h1 {
  font-weight: 900;
  font-size: 4rem;
  margin: 20px 0;
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
  color: $blue-light-3;
  max-width: 600px;
}
a {
  border: none;
  font-weight: 600;
  letter-spacing: 0.25px;
  font-family: "Lato", sans-serif;
  text-decoration: none;
  color: $blue-light;
}
a:hover {
  text-decoration: underline;
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
  margin-left: 40px;
}

@import '@/styles/media.scss';
@import '@/styles/blog.scss';
</style>
