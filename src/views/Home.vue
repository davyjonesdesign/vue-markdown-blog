<template>
  <div class="home page">
    <div class="headline">
      <h1 class="center">Davy Jones' Locker</h1>
      <p class="center">A web designer's blog about the ins and outs of designing for the web.</p>
    </div>
    <div class="sections">
      <div v-for="(section, index) in Object.keys(entries)" :key="index" class="group">
        <h5 class="center">{{section}}</h5>
        <div class="section" v-for="entry in entries[section]" :key="entry.id">
          <div class="entry" @click="$router.push({name: entry.id}); scrollToTop();">
            <div class="img-wrapper">
              <img :src="entry.image" :alt="entry.title"/>
            </div>
            <div class="entry-content">
              <h3>
              {{entry.title}}
              </h3>
              <h6 class="subtitle">{{entry.date}}</h6>
              <p>{{entry.description}}</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import BLOGENTRIES from '@/statics/data/blogs.json'

export default {
  name: 'home',
  computed: {
    entries() {
      return BLOGENTRIES
    }
  },
  methods: {
    scrollToTop() {
      window.scrollTo(0, 0);
    },
  },
}
</script>
<style lang="scss" scoped>
@import '@/styles/main.scss';

.center {
  text-align: center;
}
.headline {
  padding: 30vh 4rem 4rem;
  margin: 0;
  background-image: linear-gradient(to bottom, rgba(0, 0, 0, 0.25), rgba(0, 0, 0, 0.7), rgba(0, 0, 0, 0.9)), url('../assets/davy-jones-locker.jpg');
  background-size: cover;
  background: $text-dark;
  color: $blue-light;
  position: sticky;
  top: 0;
  & p {
    margin: auto;
    color: $blue-light-2;
  }
}
img {
  display: block;
  margin: 0 auto;
  height: 100%;
}
.img-wrapper {
  max-width: 150px;
  max-height: 200px;
  overflow: hidden;
}

h3 {
  color: $blue-light;
  margin-bottom: 0;
  cursor: pointer;
  &:hover {
    text-decoration: underline;
  }
}
.subtitle {
  color: $blue-light-2;
  font-size: .98rem;
  margin: 5px 0 15px;
  font-weight: normal;
  text-transform: uppercase;
}

p {
  margin-top: .4rem;
}

.sections {
  width: 100%;
  margin: 0 auto;
  // padding-top: 4rem;
  background: $text-dark;
  border-top: 2px solid $blue-dark;
  z-index: 10;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.group {
  // margin-bottom: 1rem;
  z-index: 100;
  display: flex;
  flex-direction: column;
  align-content: center;
  & h5 {
    display: inline-block;

    color: $blue-light-3;
    // width: auto;
    padding: 10px 6px;
    position: sticky;
    top: 0;
    font-weight: 400;
    text-transform: capitalize;
    font-size: 1rem;
    background: $blue-dark;
    min-width: 200px;
    margin: 30px 0 0;
  }
}
.entry {
  background: $blue-dark-2;
  max-width: 60vw;
  border-radius: 0;
  margin: -1px 0 -1px;
  transition: $transition;
  overflow: hidden;
  display: flex;
  border: 2px solid $blue-dark;
  cursor: pointer;
  &:hover {
    transform: translate(-4px, -5px);
    transition: $transition-fastest;
    box-shadow: 4px 5px 2px $text-dark;
    background: $text-dark;
    border-color: $blue-light;
    border-radius: $border-radius;
  } &:hover h3 {
    text-decoration: underline;
    transition: $transition-fastest;
    color: $text-light;
  } &:hover .subtitle {
    color: $blue-light-2;
  }
}
.entry-content {
  display: flex;
  flex-direction: column;
  align-content: center;
  justify-content: center;
  margin: 0 40px 0 30px;
  & h3 {
    margin-top: 10px;
  }
  & p {
    margin: 0 0 20px;
  }

}
.back-link {
  display: none;
}
@import '@/styles/media.scss';
</style>